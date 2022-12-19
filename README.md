# 111-1 AOI Technology and Application
## 專題名稱：姿態辨識 - 牛仔對決
* 指導老師：許智淵 老師
* 組員名單：電子碩二甲 江承修、電子碩一甲 林芳平

### 專題動機：
* 原本討論想做手勢辨識，並應用於門禁系統，但後來想想，太無趣了，於是突發奇想，想到了switch有款遊戲是: 牛仔對決。該遊戲是利用搖桿Sensor進行，但我們想利用Mediapipe與OpenCV來實現。
* 如下，是擷取Nintendo of America的Switch遊戲宣傳影片，其中有一款牛仔遊戲如下影片。
* 當音樂響起時代表預備，然後會聽到: fire! 雙方把槍舉起，比速度，快的一方獲勝。[原影片來源](https://www.youtube.com/watch?v=DpHDJRGuL7w)
{%youtube vIFSCeARHWk %}

### 需求：
* 架設兩攝影機，以Mediapipe分別辨識兩個人當前姿態。
* 以亂數時間倒數，決定開始時機。
* 遊戲開始判斷誰最先打中對方的頭。
* 以Mediapipe pose抓出的手部關鍵點並進行平面上的連線，若先指到對方的頭部則獲勝。
![](./需求圖片.png)

### 限制需求 (環境):
* 硬體：i7等級以上CPU IPC or PC。
* 周邊設備：IP Camera *1、顯示器 *1 。
* 作業系統：Ubuntu 20.04。
* 軟體：Python3.8+、OpenCV、Mediapipe。
* 應用環境：室內明亮的日光燈空間。


### 分析 - MediaPipe Pose：
Mediapipe是Google開發的一款套件，可實現人臉追蹤、手掌偵測、姿態偵測、人物去背…
我們將使用姿態偵測模型，該模型可標記身體中 33 個關節點的位置。我們採用其中11、13、15
等手臂關節點之數據做分析，判斷其當前動作(閒置/開槍)。[圖片來源](https://google.github.io/mediapipe/solutions/pose#python-solution-api)
![](https://github.com/JiangXiu11200/111-1_AOITechnologyandApplication/blob/main/exampleImage/%E5%88%86%E6%9E%90.png)

### Breakdown：
* 系統Breakdown
![](https://github.com/JiangXiu11200/111-1_AOITechnologyandApplication/blob/main/exampleImage/%E7%B3%BB%E7%B5%B1breakdown1.png)
*  程式模組Breakdown
![](https://github.com/JiangXiu11200/111-1_AOITechnologyandApplication/blob/main/exampleImage/%E7%B3%BB%E7%B5%B1breakdown2.png)



