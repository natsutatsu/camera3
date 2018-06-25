# camera3
import cv2

capture = cv2.VideoCapture(0) //VideeoCaptureオブジェクトを取得.引数にpcに接続されているカメラの番号を指定.1台の場合は0で良い.

while(True):  //カメラから連続的に画像を取得するためにwhile文を用いてループさせる.

    ret, frame = capture.read()  //カメラから1コマのデータを取得する.取得したデータはframeに保存される.
    
    cv2.imshow('frame',frame)  //フレームに画像を表示するメソッド.第１引数にはフレームの名前を指定する.第２引数にはcapture.read()で取得した画像データを指定する
    
    if cv2.waitKey(1) & 0xFF == ord('q'):  //キーボードから'q'が入力された時にループを抜け,画像の取得をやめる.このときは'q'でループを抜けるように設定されているが,違うアルファベットでもよい.
    
        break

capture.release()  //VideoCaptureオブジェクトを終了する

cv2.destroyAllWindows() //ウィンドウを閉じる
