# Functions and Methods
created on 2020/01/03 by LiuYueyao
## CREATE_DYNAMIC_TABLE
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

## Conversion of Currency Amounts into External Data Format
  >BAPI_CURRENCY_CONV_TO_EXTERN_9

  ## ALV
  >CALL FUNCTION 'REUSE_ALV_GRID_DISPLAY_LVC'.
## OOALV
class ALV
>CLASS LCL_ALV DEFINITION ##CLASS_FINAL .  
  PUBLIC SECTION.  
    CLASS-METHODS:  
      MTD_USER_TOOLBAR FOR EVENT TOOLBAR OF **CL_GUI_ALV_GRID**  
      IMPORTING E_OBJECT.  
    ENDCLASS.  
>CLASS LCL_ALV IMPLEMENTATION.  
  METHOD MTD_USER_TOOLBAR.  
  ENDMETHOD.

ALV object
>GO_GRID01 TYPE REF TO CL_GUI_ALV_GRID.  
CREATE OBJECT GO_GRID01.

display ALV
>CALL METHOD GO_GRID01->SET_TABLE_FOR_FIRST_DISPLAY.  
SET HANDLER LCL_ALV=>MTD_USER_TOOLBAR FOR GO_GRID01.



## FI Functions
>FI_DOCUMENT_CHANGE

>BAPI_ACC_DOCUMENT_CHECK

>BAPI_ACC_DOCUMENT_POST
