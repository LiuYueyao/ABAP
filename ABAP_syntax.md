# ABAP syntax
created on 2019/11/18 by LiuYueyao
## loop at group
    LOOP AT itab ASSIGNING FIELD-SYMBOL(<fs_group>)
    GROUP BY ( group_key = <fs_group>-key ).

      LOOP AT GROUP <fs_group>
      ASSIGNING FIELD-SYMBOL(<fs_entry>).
      ...
      ENDLOOP.
    ENDLOOP.

## DB table inner join internel table
*(replacement of "FOR ALL ENTRIES IN")*

    SELECT
      dbtab~field1,
      dbtab~field2,
    FROM dbtab
    INNER JOIN @itab AS itab_alias
    ON dbtab~field1 =  itab_alias~field1
    WHERE [something]
    INTO TABLE @itab_target.

## pointer (data reference)
    DATA object TYPE REF TO DATA.
    FIELD-SYMBOLS <fs_itab> TYPE STANDARD TABLE.

    CREATE DATA object TYPE STANDARD TABLE OF (dbtab).
    ASSIGN object->* TO <fs_itab>.

  Use \<fs_itab\> for further operations.

## time stamp
    DATA v_tmstmp TYPE TIMESTAMP.
    GET TIME STAMP FIELD v_tmstmp.

TYPE TIMESTAMP format "yyyymmddhhmmss"

## get text of selection screen field
    (eg.)
    MESSAGE E017(ZFI001)
      WITH
        %_P_GJAHR_%_APP_%-TEXT
        SPACE
        SPACE
        SPACE.

## terminate program and return to selection screen
    LEAVE SCREEN.

## get value of dynamic table
    * Get mid table fields
      DATA(LO_TABLE)  = CL_ABAP_TABLEDESCR=>DESCRIBE_BY_NAME( P_TABN ).
      DATA(LO_STRUCT) = CAST CL_ABAP_STRUCTDESCR( LO_TABLE ).
      DATA(LIT_FIELD) = LO_STRUCT->GET_DDIC_FIELD_LIST( ).

    * lock by record
      LOOP AT <LIT_MID_DATA> ASSIGNING FIELD-SYMBOL(<LW_MID>).
        CLEAR LV_VARKEY.

    *   Get record key
        LOOP AT LIT_FIELD ASSIGNING FIELD-SYMBOL(<LW_FIELD>)
          WHERE KEYFLAG = ABAP_TRUE.

    *     Get value of mid table fields
          ASSIGN COMPONENT <LW_FIELD>-FIELDNAME OF STRUCTURE <LW_MID>
          TO FIELD-SYMBOL(<LV_VALUE>).

    *     Set record key
          CONCATENATE LV_VARKEY
                      <LV_VALUE>
                 INTO LV_VARKEY.

        ENDLOOP.
      ENDLOOP.
