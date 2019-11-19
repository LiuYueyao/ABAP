# VOFM example
*Configuration for Reqs, Formulae*

## Target_1
与信消費額の算出・設定

## Procedure_1
1. ルチン登録
![Image alt text](../pictures/VOFM/1-1.png)
![Image alt text](../pictures/VOFM/1-2.png)

  **以下により、ルチンを登録する。※「900」以降の番号を指定する**
![Image alt text](../pictures/VOFM/1-3.png)

2. ルチン有効化
![Image alt text](../pictures/VOFM/1-4.png)

3. 配置  
  **T-Code:SPRO**
![Image alt text](../pictures/VOFM/1-5.png)
![Image alt text](../pictures/VOFM/1-6.png)

  **条件タイプ「ZPCA」を指定して、DB「T683S」から取得する決定表が配置対象とする**
![Image alt text](../pictures/VOFM/1-7.png)

  **代替計算タイプにルチン番号をセットする**
![Image alt text](../pictures/VOFM/1-8.png)

4. ルチンのコード編集
![Image alt text](../pictures/VOFM/1-9.png)
![Image alt text](../pictures/VOFM/1-10.png)

## Target_2
与信消費額非表示

## Procedure_2
1. ルチン登録
![Image alt text](../pictures/VOFM/2-1.png)
![Image alt text](../pictures/VOFM/2-2.png)

  **以下により、ルチンを登録する。※「900」以降の番号を指定する**
![Image alt text](../pictures/VOFM/2-3.png)

2. ルチン有効化
![Image alt text](../pictures/VOFM/2-4.png)

3. 配置  
  **T-Code:SPRO**
![Image alt text](../pictures/VOFM/2-5.png)
![Image alt text](../pictures/VOFM/2-6.png)

  **条件タイプ「ZPCA」を指定して、DB「T683S」から取得する決定表が配置対象とする**
![Image alt text](../pictures/VOFM/2-7.png)

  **限定条件にルチン番号をセットする**
![Image alt text](../pictures/VOFM/2-8.png)

4. ルチンのコード編集
![Image alt text](../pictures/VOFM/2-9.png)
![Image alt text](../pictures/VOFM/2-10.png)
