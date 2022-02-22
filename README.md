import cv2
print(cv2.__version__)

cam = cv2.VideoCapture(0, cv2.CAP_DSHOW)
cam.set(cv2.CAP_PROP_FRAME_WIDTH, 1280)
cam.set(cv2.CAP_PROP_FRAME_HEIGHT, 720)
cam.set(cv2.CAP_PROP_FPS, 30)
cam.set(cv2.CAP_PROP_FOURCC, cv2.VideoWriter_fourcc(*'MJPG'))
cam = cv2.VideoCapture('Resources/face.mp4')
while True:
    success, frame = cam.read()
    print(success)

    cv2.imshow('MBS3523', frame)
    if cv2.waitKey(100) & 0xff == ord('q'):
        break

cam.release()
cv2.destroyAllWindows()
