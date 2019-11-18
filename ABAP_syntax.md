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
