# 組裝環節

![](pic/guide/all.jpg)

## 基本安裝順序

### 二極體

1N4148是機械鍵盤上最常使用到的二極體元件，有分為`SMD`貼片式及`THT`直插式，這裡我們使用到的為貼片式，方向對應如下圖：

![](pic/guide/dio.png)

貼片式二極體相當的微小，需要用鑷子稍微轉動光線才會將它方向展示出來，我們首先的第一步就是將二極體安裝在鍵盤上頭合計`25個`位置上：

![](pic/guide/dio2.jpg)

### 熱插拔座

二極體固定完成後再來焊接固定熱插拔座：

![](pic/guide/hs.jpg)

探索者3號支援的熱插拔座有`Choc`及`GLP`兩種版本，擇一安裝即可，對應的腳位如下圖：

![](pic/guide/hs2.jpg)

安裝完將TRRS下方的跳線`P1`連接起來：

- `P1`為預設的TRRS的電源連接方案，ATMega32U4 ProMicro及RP2040 ProMicro基本都是使用這個方案。

> 若RP2040 ProMicro出現左右兩側鍵盤上的`通信問題`，請將`P1`上的焊錫移除後改至`P2`再做通信測試。

![](pic/guide/p1.jpg)

### MCU

接著將MCU依照電路板上的標示框及上頭的`VCC`、`GND`對應、晶片面朝下安裝。

> 排針可選擇直插式或可插拔的款式，為了方便測試因此照片示意圖會是可插拔的版本，大家參考一下即可。

![](pic/guide/m2.jpg)
![](pic/guide/m3.jpg)

> 可插拔排針母座安裝示意圖。

![](pic/guide/m4.jpg)

下一步將`TRRS座`及`2pin輕觸開關`安裝上去（只需安裝單邊鍵盤的話不用安裝TRRS座）。

![](pic/guide/cd1.jpg)

## Cirque 40mm觸控板模組

- 請務必將beekeeb及Keycapsss的組裝流程看過一輪，下面會統合兩篇文章的資訊：

    - [Cirque Trackpad i2c on Corne Keyboard Build Log](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)。
    - [GlidePoint Cirque Trackpad with Adapter PCB](https://keycapsss.com/help/cirque-trackpad/#spi-or-i2c)。

為了設計這把鍵盤我才會從網路通路上購入觸控板模組的拓展包來使用，接著再額外購入FFC連接座來安裝鍵盤。

- 鍵盤的結構參考beekeeb及bastardkb鍵盤Dilemma設計，FFC連接座會固定在電路板背面，跟熱插拔座在同一面（請看下圖照片對比）。
- 使用上面提及的兩篇文章來安裝拓展模組，使用銅柱長度會需要調整。
- 探索者3號使用`I2C`模式連接觸控板。

> 結構安裝照片來自beekeeb：

![](https://beekeeb.com/trackpad/side.jpg)

> 鍵盤安裝完成後側面的結構：

![](pic/guide/c1.jpg)

以下是beekeeb及Keypasss兩篇拓展板文章的統合資訊：

- `I2C`模式下需要更動的觸控板元件及需要安裝的元件：

|MCU|IC|VCC|R1電阻|R7電阻|R8電阻|4.7K上拉電阻|
|--|--|--|--|--|--|--|
|ProMicro|ATMega32U4|5V|移除|移除|移除|加裝|
|ProMicro|RP2040|3V3|移除|-|-|加裝|

### 加裝FFC連接座

![](pic/guide/c2.jpg)

使用電烙鐵焊接軟排線連接座相當困難，這裡會推薦使用加熱台或熱風槍將其用焊錫、錫漿固定在電路板上。

![](pic/guide/h1.jpg)

> 這裡特別留意會需要刷上一定量的`助焊劑`給加熱台做使用。

![](pic/guide/h2.jpg)

FFC連接座完成固定後，再將軟排線安裝固定上去。

![](pic/guide/h3.jpg)

卡榫固定好後將排線穿過下方的洞口至另一側。

![](pic/guide/h4.jpg)

### 上拉電阻

![](pic/guide/r1.jpg)

上拉電阻的部分很簡單，把針腳稍微彎折一下，插入R1、R2上對應的焊盤孔中，用焊錫固定好，多餘的針腳移除掉即可。

![](pic/guide/r2.jpg)

### FFC連接座拓展板

- 安裝拓展板時的注意事項：

    - 安裝前需將鍵盤電路板正面的I2C`跳線`都接通才可正常使用（下圖所示）。
    - FFC連接座拓展板為網路通路商所開發讓使用者自由安裝的插件模組，安裝方式參照該通路商的安裝說明文章。
    - 使用拓展板會增加該安裝位置的厚度，因此需要自行調整`銅柱的高度`。

![pcb1](pic/guide/pcb1.png)

### 擋板組合

![](pic/guide/t1.jpg)

觸控板上的電阻移除後，將觸控板本體及3片擋板組合在一起。首先，擋板A、C的洞口直徑不太一樣，視安裝的元件不同，擋板上下的順序也不同。

![t7](pic/guide/t7.png)

接著將A、B兩者對齊平放。

![](pic/guide/t2.jpg)

再來將觸控板本體放在中間，有防呆卡榫，不用擔心安裝失誤。

![](pic/guide/t3.jpg)

然後將C板疊在一起。

![](pic/guide/t4.jpg)

最後再用6mm的螺絲跟螺母將板子固定起來。

![](pic/guide/t6.jpg)
![](pic/guide/t5.jpg)

## 旋鈕編碼器

旋鈕編碼器的部分安裝相對簡單，按照對應的針腳位置安裝上去、再用焊錫固定起來即可。

![](pic/guide/e1.jpg)

## 外殼

![](pic/guide/b1.jpg)

底板的部分會按照圖中標示的位置使用上相應長度的螺絲，安裝順序接著會來說明。

首先8mm螺絲的部分會使用螺母先固定好。

![](pic/guide/b2.jpg)

4mm螺絲的部分，會跟墊片、5mm銅柱固定在一起。

![](pic/guide/b3.jpg)

接著在螺絲上頭安裝墊片後，暫且放置在一邊，待會會用到。

![](pic/guide/b4.jpg)

## 最後組裝

不管選配的部分為觸控板還是旋鈕編碼器，最後的安裝方式基本一樣。

### 觸控板

首先是搭載觸控板的部分，將電路板對應底板輕放上去，並依照圖中標示安裝對應長度的銅柱。

![](pic/guide/l1.jpg)
![](pic/guide/l2.jpg)

接著將軟排線接在觸控板上的FFC插槽內，並順著排線方向將擋板對好螺絲孔，用6mm的螺絲固定起來。

![](pic/guide/l3.jpg)

最後依序將定位板、MCU擋板用3mm螺絲鎖上。

![](pic/guide/l4.jpg)
![](pic/guide/l5.jpg)

### 旋鈕編碼器

![](pic/guide/l6.jpg)

編碼器的部分也是一樣，將電路板放在底板上，並安裝好對應長度的銅柱。

接著再將旋鈕帽蓋安裝上去。

![](pic/guide/l7.jpg)

編碼器這裡的擋板部分堆疊順序會跟觸控板相反，將擋板用螺絲螺帽固定好之後，就可以直接安裝了。

![](pic/guide/t8.png)
![](pic/guide/l8.jpg)

最後將鍵盤翻至背面，貼上腳貼就完成了。

![](pic/guide/l9.jpg)

## 安裝軸帽

鍵軸及鍵帽可以最後再安裝，看個人選擇，這裡安裝使用的是凱華Choc v2黑雲軸。

![](pic/info/info1.jpg)

鍵帽使用的是太豪THT，十字矮軸、無刻的版本。

![](pic/info/info2.jpg)

完成！

![](pic/info/info4.jpg)

### 韌體燒錄

韌體安裝順序可不同，若要在組裝鍵盤之前先燒錄的話，請對應使用的MCU，使用對應的燒錄方式。

- 組裝鍵盤前：

    - ATMega32U4 ProMicro：可使用`QMK Toolbox`及`QMK MSYS`進行燒錄。
    - RP2040 ProMicro：啟動`RP_BOOT`模式，將`.uf2`韌體燒進硬碟裡即可。

> `RP_BOOT`模式有兩種方式可以啟動：
> 1. 將MCU上的`BOOT`按鈕按住後接入電腦後啟動。
> 2. 接入電腦後按住`BOOT`按鈕1秒後再按`RESET`按鈕後啟動。

- 組裝鍵盤後：

    - ATMega32U4 ProMicro：可使用`QMK Toolbox`及`QMK MSYS`進行燒錄，`RESET`按鈕壓一下就可啟動燒錄模式。
    - RP2040 ProMicro：電路板上的`RESET`輕觸開關`按2下之後1秒放開`，會啟動`RP_BOOT`模式，將`.uf2`韌體燒進硬碟裡即可。

> MCU的背面也有對應的`RESET`及`BOOT`孔可以用鑷子觸發，不用擔心燒錄問題。












