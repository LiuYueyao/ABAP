# Functions and Methods
created on 2020/01/03 by LiuYueyao
* CREATE_DYNAMIC_TABLE
  >CALL METHOD CL_ALV_TABLE_CREATE=>CREATE_DYNAMIC_TABLE  
    EXPORTING   
  \*    I_STYLE_TABLE="Type CHAR01  
    IT_FIELDCATALOG= it_obligatory "Type LVC_T_FCAT  
  \*    I_LENGTH_IN_BYTE ="Type BOOLEAN  
  \*  IMPORTING  
  \*    EP_TABLE  ="Type Ref To DATA  
  \*    E_STYLE_FNAME ="Type LVC_FNAME  
  \*  EXCEPTIONS  
  \*    GENERATE_SUBPOOL_DIR_FULL = 1  
  \*    OTHERS                    = 2  
    .  
  IF SY-SUBRC <> 0.  
  \* Implement suitable error handling here  
  ENDIF.  

  IT_FIELDCATALOG: *Field Catalog, default data type char10*  
EP_TABLE: *Pointer to Dynamic Data Table*  
E_STYLE_FNAME:  *ALV Control: Field Name of Internal Table Field*  
