# 組裝環節

![](pic/guide/all.jpg)

## 基本安裝順序

### 二極體

1N4148是機械鍵盤上最常使用到的二極體元件，有分為SMD貼片式及THT直插式，這裡我們使用到的為貼片式，方向對應如下圖：

![](pic/guide/dio.png)

貼片式二極體相當的微小，需要用鑷子稍微轉動光線才會將它方向展示出來，我們首先的第一步就是將二極體安裝在鍵盤上頭合計25個位置上：

![](pic/guide/dio2.jpg)

### 熱插拔座

二極體固定完成之後再來焊接固定熱插拔座：

![](pic/guide/hs.jpg)

探索者3號支援的熱插拔座有Choc及GLP兩種版本，請擇一安裝即可，對應的腳位如下圖：

![](pic/guide/hs2.jpg)

安裝完畢後請將TRRS下方的跳線P1連接起來：

- P1為預設的TRRS的電源連接方案，ATMega32U4 ProMicro及RP2040 ProMicro基本都是使用這個方案。

> 若RP2040 ProMicro出現左右兩側鍵盤上的通信問題，請將P1上的焊錫移除後改至P2再做通信測試。

![](pic/guide/p1.jpg)

### MCU

接著將MCU準備好，並且依照電路板上的標示框及上頭的VCC、GND對應、晶片面朝下安裝。

針腳可以選擇直插式或可插拔的款式，為了方便測試照片示意圖會是可插拔的版本，大家參考一下即可。

![](pic/guide/m2.jpg)
![](pic/guide/m3.jpg)

> 可插拔排針母座安裝示意圖。

![](pic/guide/m4.jpg)

下一步將TRRS座及2pin的輕觸開關安裝上去（只需安裝單邊鍵盤的話請跳過此步驟）。

![](pic/guide/cd1.jpg)

## 選配安裝部分

### Cirque 40mm觸控板模組

- 請務必將beekeeb及Keycapsss的組裝流程看過一輪，這裡我會統合兩篇Guide的資訊：

    - [Cirque Trackpad i2c on Corne Keyboard Build Log](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)。
    - [GlidePoint Cirque Trackpad with Adapter PCB](https://keycapsss.com/help/cirque-trackpad/#spi-or-i2c)。

這裡先告訴大家我是為了設計這把鍵盤才會從網路通路上購入觸控板模組的拓展包來使用，接著再額外購入FFC連接座來安裝鍵盤。

- 鍵盤的結構參考beekeeb設計，FFC連接座會固定在鍵盤背面，跟熱插拔座焊接在同一面（請看下圖照片對比）。
- 使用上面提及的兩篇文章來安裝拓展模組，使用銅柱長度會需要調整。

> 結構安裝照片來自beekeeb：

![](https://beekeeb.com/trackpad/side.jpg)

> 鍵盤安裝完成後側面的結構：

![](pic/guide/c1.jpg)

以下是beekeeb及Keypasss兩篇拓展板文章的統合資訊：

- I2C模式下需要更動的觸控板及安裝元件：

|MCU|IC|VCC|R1電阻|R7電阻|R8電阻|4.7K上拉電阻|
|--|--|--|--|--|--|--|
|ProMicro|ATMega32U4|5V|移除|移除|移除|加裝|
|ProMicro|RP2040|3V3|移除|-|-|加裝|

#### 加裝FFC連接座

![](pic/guide/c2.jpg)

使用電烙鐵焊接軟排線連接座是相當困難的事情，這裡會推薦使用加熱台或熱風槍將其用焊錫、錫漿固定在電路板上。

![](pic/guide/h1.jpg)

> 這裡特別留意會需要刷上一定量的助焊劑給加熱台做使用。

![](pic/guide/h2.jpg)

FFC連接座完成固定後，再將軟排線安裝固定上去。

![](pic/guide/h3.jpg)

卡榫固定好後將排線穿過下方的洞口至另一側。

![](pic/guide/h4.jpg)





### 旋鈕編碼器














