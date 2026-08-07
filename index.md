# Ball Tracking Robot
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```


|:--:|:--:|:--:|:--:|
| Ethan L | Palo Alto High School | Electrical Engineering | Incoming Junior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/nYEQcfX-JrY?si=0QiwvCethCimm3Qn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Since my last milestone, I've added two modifications to my robot. The first was adding gesture control, which allows it to switch between two modes: either halting the motors completely or allowing it to function in its normal tracking mode. The second modification was mounting my camera on a pan-tilt module, which allows it to move up and down, and side to side.

In addition, I've added a button on a breadboard which allows the robot to stop or start scanning for new gestures. This function allows the robot to avoid scanning for new gestures unnecessarily when it's already in a currently desired mode.

My biggest challenge at BSE was definitely setting up the remote connection between my Mac and the Pi. Because the Pi doesn't have a physical monitor, I had to create a remote connection between my Mac and the Raspberry Pi. This starts with writing data onto the Pi, including a hostname, username, and Wi-Fi connection. A major problem I had was that the Pi kept storing old information, which prevented a connection. This was my greatest problem because until I could fix it, I couldn't troubleshoot my robot or test any code at all.

My greatest triumph was setting up the gesture control function in my robot. Instead of just detecting color for the ball, it now also detects shape, which allows it to detect my skin color and the shape of my hand.

# Hardware / electronics

Learned the difference between BOARD and BCM pin numbering, and had to standardize my whole script on BCM since ServoKit/Blinka forces it
Learned how ultrasonic sensors measure distance by timing a ping and its echo, then converting that time into distance
Learned why the Pi's GPIO pins can't drive motors on their own, and how an H-bridge steps in as the driver
Learned how PWM controls motor speed by switching power on and off rapidly, and how driving the wheels differently makes the robot turn
Learned how to control my pan-tilt camera mount over I2C using a separate PCA9685 board, and figured out that jitter was a power issue, not a wiring issue
Ran into breadboard wiring issues with split power rails and shared ground pins, and learned to isolate them with a direct jumper-wire test

# Computer vision / gesture recognition

Learned how my ball-tracking system finds "red" by converting frames to HSV and thresholding a hue range, rather than recognizing the ball's shape
Used OpenCV to find the largest region matching a color mask through contours and blob detection
Learned to isolate my hand using YCrCb color space, then classify gestures by aspect ratio, solidity, and convexity defects to tell a fist from a peace sign
Realized that image-processing kernels built for ball detection can quietly mess up gesture detection when reused without adjusting them

# Debugging methodology

Learned to isolate variables by writing a minimal test script for just one component, instead of debugging blind inside the full robot script
Learned to read printed diagnostic values like area, aspect, and solidity to tune thresholds against real data instead of guessing

# Tooling / infrastructure

Set up SSH and RealVNC for headless remote control of the Pi from my Mac, and troubleshot stale network/connection info along the way



# Second Milestone



<iframe width="560" height="315" src="https://www.youtube.com/embed/Lsc_K4YmL-I?si=gdO5KxqG5OnVFosu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


- I finished construction of the whole robot, with 2 ultrasonic sensors on the left and right of the hood, and the camera in the center. The Rasberry Pi sits behind these 3 components with the breadboard sitting on top of a portable charger in front of a battery pack. In addition, there is an H-Bridge to allow the motors to spin in other directions and wires connecting all main components together allowing them to work in unison. Next, I optimized the code to further increase the efficiency of the robot, allowing it to move in quicker shorter movements rather than longer slower movements. Lastly, I decreased the resolution and reduced the number of loops the code had to increase the speed at which my camera could process things.
- A problem that I overcame was the wiring of my robot and how quickly it became complicated. Keeping track of 3 different components using a single breadboard was extremely challenging, most of the time I couldn't even tell where each wire led to. I fixed this by organizing my breadboard into sections, one for each component, this allowed me to keep track of anything without it becoming too complicated. This method also allowed me to add more wires as I worked. 
- Before my final milestone, I would like to complete multiple modifications to my robot. A couple modifications I had in mind are using gesture controls, mounting the camera on a pan-tilt camera and allowing the camera to detect objects other than a ball.

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/Hk_1bXw5oVo?si=jYADtwLQSgQXHO5M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


- Currently, my project is comprised of a chasis, motors, a Rasberry Pi, ultrasonic sensors, batteries, and an H-Bridge. First, the chasis is the base of my robot, it allows the robot to move in different directions with the aid of the motors and wheels. Second, the Rasberry Pi acts as the brain, it stores code and information for the ultrasonic sensors and motors to process, in which they can then execute. Lastly, the batteries power the H-Bridge, which allows for a different direction of spin from the motors, altering the way that they can move. 
- I've constructed a majority of my robot so far, aside from the camera which was defective, the ultrasonic sensors are connected to a Rasberry Pi through a breadboard and wires, and similiarly with the motors and H-Bridge. 
- A challenge I faced was setting up the ssh. Before connecting the Rasberry Pi remotely to my computer, I had to write information into the Rasberry Pi, giving it a username, hostname and a network to connect to. A problem I had with this was that the Rasberry Pi kept storing old information, stopping any connection to my Mac from happening. I overcame this my rewriting the storage on the Pi and resetting it. For my future milestones, I hope to finish my base project and start adding modifications to it.
- My plan is to finish the base project by this week, and start on modifications the next. I want to have as much time as possible to have creative freedom over my own project. 

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code

<div style="
  height: 350px;
  overflow-y: auto;
  overflow-x: hidden;
  background-color: #1e1e1e;
  color: white;
  padding: 15px;
  border-radius: 8px;
">
  <pre style="
    margin: 0;
    white-space: pre-wrap;
    overflow-wrap: anywhere;
    word-break: break-word;
    font-family: Consolas, monospace;
    font-size: 14px;
    line-height: 1.5;
  "><code>

from picamera2 import Picamera2
import RPi.GPIO as GPIO
import time
import cv2
import numpy as np
import math
from pynput import keyboard
from adafruit_servokit import ServoKit

GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)

GPIO_TRIGGER1 = 5                                             
GPIO_ECHO1 = 6                         

GPIO_TRIGGER3 = 13                                             
GPIO_ECHO3 = 19                        

MOTOR1B = 9                             
MOTOR1E = 10                 

MOTOR2B = 25                             
MOTOR2E = 24                 

LED_PIN = 27                                                                     

GPIO_BUTTON = 26                 
BUTTON_DEBOUNCE = 0.3            

GPIO.setup(GPIO_TRIGGER1,GPIO.OUT)           
GPIO.setup(GPIO_ECHO1,GPIO.IN)            
GPIO.setup(GPIO_TRIGGER3,GPIO.OUT)           
GPIO.setup(GPIO_ECHO3,GPIO.IN)
GPIO.setup(LED_PIN,GPIO.OUT)
GPIO.setup(GPIO_BUTTON, GPIO.IN, pull_up_down=GPIO.PUD_UP)

GPIO.output(GPIO_TRIGGER1, False)
GPIO.output(GPIO_TRIGGER3, False)

SONAR_SETTLE = 0.000002
SONAR_START_TIMEOUT = 0.02                                     
SONAR_ECHO_TIMEOUT = 0.03                                          

def sonar(GPIO_TRIGGER, GPIO_ECHO):
      GPIO.output(GPIO_TRIGGER, False)
      time.sleep(SONAR_SETTLE)
      GPIO.output(GPIO_TRIGGER, True)
      time.sleep(0.00001)
      GPIO.output(GPIO_TRIGGER, False)

      begin = time.perf_counter()
      start = begin
      timeout1 = begin + SONAR_START_TIMEOUT
      while GPIO.input(GPIO_ECHO) == 0 and time.perf_counter() < timeout1:
            start = time.perf_counter()

      stop = start
      timeout2 = start + SONAR_ECHO_TIMEOUT
      while GPIO.input(GPIO_ECHO) == 1 and time.perf_counter() < timeout2:
            stop = time.perf_counter()

      elapsed = stop - start
      distance = elapsed * 17000.0
      return distance

GPIO.setup(MOTOR1B, GPIO.OUT)
GPIO.setup(MOTOR1E, GPIO.OUT)
GPIO.setup(MOTOR2B, GPIO.OUT)
GPIO.setup(MOTOR2E, GPIO.OUT)

PWM_FREQ = 1000
DEFAULT_SPEED = 55

pwm_1b = GPIO.PWM(MOTOR1B, PWM_FREQ); pwm_1b.start(0)
pwm_1e = GPIO.PWM(MOTOR1E, PWM_FREQ); pwm_1e.start(0)
pwm_2b = GPIO.PWM(MOTOR2B, PWM_FREQ); pwm_2b.start(0)
pwm_2e = GPIO.PWM(MOTOR2E, PWM_FREQ); pwm_2e.start(0)

def forward(speed=DEFAULT_SPEED):
      pwm_1b.ChangeDutyCycle(speed); pwm_1e.ChangeDutyCycle(0)
      pwm_2b.ChangeDutyCycle(speed); pwm_2e.ChangeDutyCycle(0)

def reverse(speed=DEFAULT_SPEED):
      pwm_1b.ChangeDutyCycle(0); pwm_1e.ChangeDutyCycle(speed)
      pwm_2b.ChangeDutyCycle(0); pwm_2e.ChangeDutyCycle(speed)

def rightturn(speed=DEFAULT_SPEED):
      pwm_1b.ChangeDutyCycle(0); pwm_1e.ChangeDutyCycle(speed)
      pwm_2b.ChangeDutyCycle(speed); pwm_2e.ChangeDutyCycle(0)

def leftturn(speed=DEFAULT_SPEED):
      pwm_1b.ChangeDutyCycle(speed); pwm_1e.ChangeDutyCycle(0)
      pwm_2b.ChangeDutyCycle(0); pwm_2e.ChangeDutyCycle(speed)

def stop():
      pwm_1b.ChangeDutyCycle(0); pwm_1e.ChangeDutyCycle(0)
      pwm_2b.ChangeDutyCycle(0); pwm_2e.ChangeDutyCycle(0)

kit = ServoKit(channels=16)
PAN = 1                               
TILT = 0                        
PAN_TILT_STEP = 5
PAN_TILT_MIN_ANGLE = 10
PAN_TILT_MAX_ANGLE = 170

for ch in (PAN, TILT):
    kit.servo[ch].actuation_range = 180

pan_angle = 90
tilt_angle = 90
kit.servo[PAN].angle = pan_angle
kit.servo[TILT].angle = tilt_angle

def clamp_pan_tilt(angle):
    return max(PAN_TILT_MIN_ANGLE, min(PAN_TILT_MAX_ANGLE, angle))

def on_key_press(key):
    global pan_angle, tilt_angle
    if key == keyboard.Key.left:
        pan_angle = clamp_pan_tilt(pan_angle - PAN_TILT_STEP)
        kit.servo[PAN].angle = pan_angle
    elif key == keyboard.Key.right:
        pan_angle = clamp_pan_tilt(pan_angle + PAN_TILT_STEP)
        kit.servo[PAN].angle = pan_angle
    elif key == keyboard.Key.up:
        tilt_angle = clamp_pan_tilt(tilt_angle + PAN_TILT_STEP)
        kit.servo[TILT].angle = tilt_angle
    elif key == keyboard.Key.down:
        tilt_angle = clamp_pan_tilt(tilt_angle - PAN_TILT_STEP)
        kit.servo[TILT].angle = tilt_angle
    elif hasattr(key, 'char') and key == keyboard.KeyCode.from_char('c'):
        pan_angle, tilt_angle = 90, 90
        kit.servo[PAN].angle = pan_angle
        kit.servo[TILT].angle = tilt_angle
    print(f"[pan/tilt] Pan: {pan_angle:3d}   Tilt: {tilt_angle:3d}")

keyboard_listener = keyboard.Listener(on_press=on_key_press)
keyboard_listener.daemon = True
keyboard_listener.start()
print("Gimbal: Arrow keys pan/tilt the camera | c = center gimbal")
print(f"Gimbal start -> Pan: {pan_angle}   Tilt: {tilt_angle}")

KERN_DILATE = np.ones((8,8),np.uint8)
KERN_ERODE  = np.ones((3,3),np.uint8)

KERN_ERODE_SKIN  = np.ones((3,3),np.uint8)
KERN_DILATE_SKIN = np.ones((3,3),np.uint8)

def segment_colour(frame):                                             
    hsv_roi = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
    mask_1 = cv2.inRange(hsv_roi, np.array([160, 160, 10]), np.array([180, 255, 255]))
    mask_2 = cv2.inRange(hsv_roi, np.array([0, 160, 10]), np.array([10, 255, 255]))
    mask = mask_1 | mask_2
    mask = cv2.erode(mask, KERN_ERODE)
    mask = cv2.dilate(mask, KERN_DILATE)
    return mask

def find_blob(blob):
    largest_contour=0
    cont_index=0
    contours, hierarchy = cv2.findContours(blob, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    for idx, contour in enumerate(contours):
        area=cv2.contourArea(contour)
        if (area > largest_contour):
            largest_contour=area
            cont_index=idx
    r=(0,0,2,2)
    if len(contours) > 0:
        r = cv2.boundingRect(contours[cont_index])
    return r, largest_contour

def target_hist(frame):
    hsv_img=cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
    hist=cv2.calcHist([hsv_img],[0],None,[50],[0,255])
    return hist

DEBUG = True

SKIN_LOWER = np.array([0, 133, 77], dtype=np.uint8)
SKIN_UPPER = np.array([255, 173, 127], dtype=np.uint8)

MIN_HAND_AREA = 800
DEFECT_DEPTH_THRESHOLD = 3500
GESTURE_HOLD_FRAMES = 3
MODE_SWITCH_COOLDOWN = 1.0

def segment_skin(frame):
    ycrcb = cv2.cvtColor(frame, cv2.COLOR_BGR2YCrCb)
    mask = cv2.inRange(ycrcb, SKIN_LOWER, SKIN_UPPER)
    mask = cv2.GaussianBlur(mask, (3, 3), 0)
    mask = cv2.erode(mask, KERN_ERODE_SKIN)
    mask = cv2.dilate(mask, KERN_DILATE_SKIN)
    return mask

def count_fingers(contour):
    hull_idx = cv2.convexHull(contour, returnPoints=False)
    if hull_idx is None or len(hull_idx) < 4:
        return 0
    try:
        defects = cv2.convexityDefects(contour, hull_idx)
    except cv2.error:
        return 0
    if defects is None:
        return 0

    finger_gaps = 0
    for i in range(defects.shape[0]):
        s, e, f, d = defects[i, 0]
        start = np.array(contour[s][0], dtype=float)
        end = np.array(contour[e][0], dtype=float)
        far = np.array(contour[f][0], dtype=float)

        a = np.linalg.norm(end - start)
        b = np.linalg.norm(far - start)
        c = np.linalg.norm(end - far)
        if b == 0 or c == 0:
            continue
        cos_angle = (b**2 + c**2 - a**2) / (2 * b * c)
        cos_angle = max(-1.0, min(1.0, cos_angle))
        angle = math.acos(cos_angle)

        if angle <= math.pi / 2 and d > DEFECT_DEPTH_THRESHOLD:
            finger_gaps += 1

    return min(finger_gaps + 1, 5) if finger_gaps > 0 else 0

FLAT_HAND_MIN_ASPECT = 1.35                                          
FIST_MAX_ASPECT = 1.15                                                           
FIST_MIN_SOLIDITY = 0.85                                                  

def classify_gesture(contour, bounding_rect):
    x, y, w, h = bounding_rect
    area = cv2.contourArea(contour)
    if area <= 0:
        return None

    aspect = h / float(w) if w > 0 else 0

    hull = cv2.convexHull(contour)
    hull_area = cv2.contourArea(hull)
    solidity = area / hull_area if hull_area > 0 else 0

    if DEBUG:
        print(f"[gesture] area={area:.0f}  aspect={aspect:.2f}  solidity={solidity:.2f}")

    if aspect > FLAT_HAND_MIN_ASPECT and area > MIN_HAND_AREA:
        return "flat_hand"

    if aspect < FIST_MAX_ASPECT and solidity > FIST_MIN_SOLIDITY and area > MIN_HAND_AREA:
        return "fist"

    finger_count = count_fingers(contour)
    if DEBUG:
        print(f"[gesture] finger_count={finger_count}")

    if finger_count == 2:
        return "peace"

    return None

GESTURE_MODE_MAP = {
    "peace": "STOP",
    "fist":  "TRACK",
}

current_mode = "TRACK"
pending_gesture = None
pending_count = 0
last_mode_switch_time = 0

gesture_scanning_enabled = True

def update_mode_from_frame(frame):
    global current_mode, pending_gesture, pending_count, last_mode_switch_time, gesture_scanning_enabled

    if not gesture_scanning_enabled:
        return

    skin_mask = segment_skin(frame)
    if DEBUG:
        cv2.imshow("Skin mask", skin_mask)

    contours, _ = cv2.findContours(skin_mask, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

    gesture = None
    if contours:
        largest = max(contours, key=cv2.contourArea)
        area = cv2.contourArea(largest)
        if DEBUG:
            print(f"[gesture] largest skin blob area = {area:.0f} (need >= {MIN_HAND_AREA})")
        if area >= MIN_HAND_AREA:
            rect = cv2.boundingRect(largest)
            gesture = classify_gesture(largest, rect)
            if DEBUG:
                cv2.drawContours(frame, [largest], -1, (255, 0, 0), 2)
                cv2.drawContours(frame, [cv2.convexHull(largest)], -1, (0, 255, 0), 2)
                print(f"[gesture] classified as: {gesture}")

    if gesture is None:
        pending_gesture = None
        pending_count = 0
        return

    if gesture == pending_gesture:
        pending_count += 1
    else:
        pending_gesture = gesture
        pending_count = 1

    now = time.time()
    if (pending_count >= GESTURE_HOLD_FRAMES
            and gesture in GESTURE_MODE_MAP
            and (now - last_mode_switch_time) > MODE_SWITCH_COOLDOWN):
        new_mode = GESTURE_MODE_MAP[gesture]
        if new_mode != current_mode:
            print(f"Gesture '{gesture}' detected -> switching mode to {new_mode}")
            current_mode = new_mode
            last_mode_switch_time = now
            gesture_scanning_enabled = False
            print("[gesture] SCANNING DISABLED. Press reset button to re-enable.")
        pending_count = 0

camera = Picamera2()
config = camera.create_preview_configuration(main={"size": (160, 120), "format": "RGB888"})
camera.configure(config)
camera.start()

time.sleep(0.1)

flag=0

initial=2500
initial2=6700
MIN_BLOB_AREA = 10
OBSTACLE_DISTANCE = 10
AVOID_DISTANCE = 8
SEARCH_TURN_TIME = 0.08
AVOID_TURN_TIME = 0.04
FORWARD_TIME = 0.05
CENTER_TURN_TIME = 0.03
SPIN_TURN_TIME = 0.1

PROFILE = True
PROFILE_REPORT_EVERY = 30
last_loop_time = time.perf_counter()

button_last_press_time = 0

GESTURE_CHECK_EVERY_N_FRAMES = 2
frame_counter = 0

try:
    while True:
          now = time.perf_counter()
          loop_dt = now - last_loop_time
          last_loop_time = now

          frame = camera.capture_array()
          frame = cv2.flip(frame, 1)

          if GPIO.input(GPIO_BUTTON) == GPIO.LOW:
              if (time.time() - button_last_press_time) > BUTTON_DEBOUNCE:
                  button_last_press_time = time.time()
                  if not gesture_scanning_enabled:
                      gesture_scanning_enabled = True
                      print("[button] Reset pressed -> gesture scanning RE-ENABLED")
                  else:
                      print("[button] Reset pressed (already enabled)")

          frame_counter += 1
          gesture_dt = 0.0
          if gesture_scanning_enabled and (frame_counter % GESTURE_CHECK_EVERY_N_FRAMES == 0):
                t0 = time.perf_counter()
                update_mode_from_frame(frame)
                gesture_dt = time.perf_counter() - t0

          if PROFILE and frame_counter % PROFILE_REPORT_EVERY == 0:
                fps = 1.0 / loop_dt if loop_dt > 0 else 0.0
                scan_status = "ON" if gesture_scanning_enabled else "OFF"
                print(f"[perf] loop: {fps:.1f} fps ({loop_dt*1000:.1f} ms/frame)  "
                      f"gesture check: {gesture_dt*1000:.1f} ms  mode={current_mode}  scan={scan_status}")

          if current_mode == "STOP":
                stop()
                GPIO.output(LED_PIN, GPIO.LOW)
                cv2.imshow("Camera feed", frame)
                if(cv2.waitKey(1) & 0xff == ord('q')):
                      break
                continue

          if current_mode == "SPIN":
                rightturn()
                time.sleep(SPIN_TURN_TIME)
                stop()
                cv2.imshow("Camera feed", frame)
                if(cv2.waitKey(1) & 0xff == ord('q')):
                      break
                continue

          active_initial2 = initial2 if current_mode == "TRACK" else initial2 * 2

          centre_x=0.
          centre_y=0.
          mask_red=segment_colour(frame)
          loct,area=find_blob(mask_red)
          x,y,w,h=loct

          if (w*h) < MIN_BLOB_AREA:
                found=0
          else:
                found=1
                simg2 = cv2.rectangle(frame, (x,y), (x+w,y+h), 255,2)
                centre_x=x+((w)/2)
                centre_y=y+((h)/2)
                cv2.circle(frame,(int(centre_x),int(centre_y)),3,(0,110,255),-1)
                centre_x-=80
                centre_y=60-centre_y

          GPIO.output(LED_PIN,GPIO.LOW)

          if(found==0):
                if flag==0:
                      rightturn()
                else:
                      leftturn()
                time.sleep(SEARCH_TURN_TIME)
                stop()

          elif(found==1):
                if(area<initial):
                      distanceR = sonar(GPIO_TRIGGER3,GPIO_ECHO3)
                      distanceL = sonar(GPIO_TRIGGER1,GPIO_ECHO1)
                      if(distanceR<OBSTACLE_DISTANCE or distanceL<OBSTACLE_DISTANCE):
                            if distanceR>=AVOID_DISTANCE:
                                  rightturn()
                                  time.sleep(AVOID_TURN_TIME)
                                  forward()
                                  time.sleep(AVOID_TURN_TIME)
                                  leftturn()
                                  time.sleep(AVOID_TURN_TIME)
                                  stop()
                            elif distanceL>=AVOID_DISTANCE:
                                  leftturn()
                                  time.sleep(AVOID_TURN_TIME)
                                  forward()
                                  time.sleep(AVOID_TURN_TIME)
                                  rightturn()
                                  time.sleep(AVOID_TURN_TIME)
                                  stop()
                            else:
                                  stop()
                                  time.sleep(0.05)
                      else:
                            forward()
                            time.sleep(FORWARD_TIME)
                            stop()

                elif(area<active_initial2):
                      distanceR = sonar(GPIO_TRIGGER3,GPIO_ECHO3)
                      distanceL = sonar(GPIO_TRIGGER1,GPIO_ECHO1)
                      if(distanceR>OBSTACLE_DISTANCE and distanceL>OBSTACLE_DISTANCE):
                            if(centre_x<=-20 or centre_x>=20):
                                  if(centre_x<0):
                                        flag=1
                                        leftturn()
                                        time.sleep(CENTER_TURN_TIME)
                                        stop()
                                  elif(centre_x>0):
                                        flag=0
                                        rightturn()
                                        time.sleep(CENTER_TURN_TIME)
                                        stop()
                            else:
                                  forward()
                                  time.sleep(0.03)
                                  stop()
                      else:
                            stop()
                            time.sleep(0.05)

                else:
                      GPIO.output(LED_PIN,GPIO.HIGH)
                      stop()
                      time.sleep(0.2)

          cv2.imshow("Camera feed", frame)
          cv2.imshow("Red mask", mask_red)

          if(cv2.waitKey(1) & 0xff == ord('q')):
                break

except KeyboardInterrupt:
    print("Shutting down...")
finally:
    keyboard_listener.stop()
    camera.stop()
    cv2.destroyAllWindows()
    for p in (pwm_1b, pwm_1e, pwm_2b, pwm_2e):
        p.stop()
    GPIO.cleanup()

  </code></pre>
</div>

# Bill of Materials


| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Rasberry Pi Kit | Brain of the robot | $147.69 | <a href="https://www.amazon.com/RasTech-Raspberry-Starter-Heatsink-Screwdriver/dp/B0C8LV6VNZ/ref=sr_1_4?crid=3506HY00MCGVM&dib=eyJ2IjoiMSJ9._zkM62vSQ8p7tNr88715LdMv_qHh72Je-tkF9PXEa3chDE53QT4aZu4AGAb4ihE61QY4ZD55nKF6Fp2Kfs8t7AbafM_JrlJFfHo9OB4eAVGqa0EB-7aoBQHPmhKHZ2MW8ny-Kd44bMVlVxPlTWVk5YHIN5P3uKVqrE5Dcal0rKkHny-O6Xyb5ux2AOU6OwVbkag_bqBX66RQNRrgBuz-0pS43mcx93IZTQA9R8NaJJypYU2HAycp-XicTFmyU60a01Nfm9iuyo6B9yA8ppN3OQQyJ-NQ9xyNPxfTLwkqtng.yAYpU6outhQcZmOZhN9Wb6yTw7A85CNUbXZguGInZNg&dib_tag=se&keywords=raspberry%2Bpi%2Bkit&qid=1718848547&s=electronics&sprefix=rasbperry%2Bpi%2Bkit%2Celectronics%2C83&sr=1-4&th=1"> Link </a> |
| Robot Chassis | Base of the robot, allows components to be put onto it aswell | $18.99 | <a href="https://www.amazon.com/Hosyond-Display-1024%C3%97600-Capacitive-Raspberry/dp/B09XKC53NH/ref=sr_1_3?crid=1KKB9WC62OIAD&keywords=raspberry%2Bpi%2Bips&qid=1685911698&s=electronics&sprefix=raspberry%2Bpi%2Bips%2B%2Celectronics%2C87&sr=1-3&th=1#customerReviews"> Link </a> |
| Screwdriver Kit | Tighten Screws | $5.94 | <a href="https://www.amazon.com/Small-Screwdriver-Set-Mini-Magnetic/dp/B08RYXKJW9/"> Link </a> |
| Ultrasonic Sensor | Read Distance | $9.99 | <a href="https://www.amazon.com/WWZMDiB-HC-SR04-Ultrasonic-Distance-Measuring/dp/B0CQCCGXCP/ref=sr_1_1_sspa?crid=3J2JR973WKPHO&dib=eyJ2IjoiMSJ9.E2SIkElJhtFWCJCHL5Q6Y73Ys_HCMPRVFCIrG_zKv4Og7BdZNtr69Mkju140lhlfzFGQuY542jpsp8FMrtV9d2hCBI7D8lYTH9bcgDXZhs4941uj-d1D69ZYdKmAI1Jig3VmYXOl3axVQ8Jq5L3nGRymNMtNbxkaFqGNyzkq4p37hhxU6jheuoaMo3Onz2FE9ILThkjUbdxRNW3rrZgZ7bYj9mf-yav85hBAmNduYyo.EneY3GmHDfDjDwhdUdDQ4Ktk6fECH62Adb42cEkehRc&dib_tag=se&keywords=ultrasonic%2Bsensor&qid=1715961326&sprefix=ultrasonic%2Bsensor%2Caps%2C72&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1"> Link </a> |
| H Bridges | Allow the motors to spin in different directions | $8.99 | <a href="https://www.amazon.com/ACEIRMC-Stepper-Controller-2-5-12V-H-Bridge/dp/B0923VMKSZ/"> Link </a> |
| Pi Cam | Capturing live video feed, reporting coordinates  | $12.86 | <a href="https://www.amazon.com/gp/product/B07RWCGX5K/ref=ox_sc_act_title_1?smid=A2IAB2RW3LLT8D&psc=1"> Link </a> |
| Electronics Kit | Breadboard and wires are used for connecting components | $11.98 | <a href="https://www.amazon.com/EL-CK-002-Electronic-Breadboard-Capacitor-Potentiometer/dp/B01ERP6WL4/ref=sr_1_4?crid=30T5LTYVQLQ7Z&dib=eyJ2IjoiMSJ9.XZtpck6Llt4UIuYeKM4X3BoXzDuzolZMTCtFDj-oTh1vuIi0HYJZJEdpS-MCdGCK1AWUbUmgoEswoRPxGUSKeGRTzsciRE_l2Vrp8FGX1SxK-HmibPNyHBEtkFJKo_OYmMhkhdCJ4OIH38ALRfFvrXZ7OU5faZVvkTBqod8p7UZYwNwdLCcimwFWGWKaDa-gbbx_TGk7lYQmEbrzeL4UXM-gW3RDtuOV0dCykxwyvYJKCCcOhrK3f18N4NZjiqL_Y5noE1rQTmwyFcG67DzgpNaUPanwIQaYfCe5mgD-njY.v6mU1wYX4M5ShCiyrZMey0hbOwvqLszD8axpHbKlA6I&dib_tag=se&keywords=mini+breadboard+kit&qid=1716419767&s=electronics&sprefix=mini+breadboard+kit%2Celectronics%2C106&sr=1-4"> Link </a> |
| Motors | Spins wheels so robot can move | $11.98 | <a href="https://www.amazon.com/AEDIKO-Motor-Gearbox-200RPM-Ratio/dp/B09N6NXP4H/ref=sr_1_4?crid=1JP29NIWBLH2M&dib=eyJ2IjoiMSJ9.Wq3jKgOLbqtEP772vMD4pV5f-w3PLBdEpKqguykXOb0JFO14f4Dq0m_VDVUMUFtR8WFINUEticI3GXcoGqwXPqK9yIh04PhCktgccMz9zAUiKXMJPwmOTUp_6av3XuFD0lXo9WngN9iKI6YgZrhEEs9qnqbcB1GnvgntCdKz8Q1dFuNu61NgSE6Z8vBk3FRpaNcr1lCI7FApTiNi0Qce8gbfmMn6oUggZQHpIOKKZ6s.M7WsZ_ZZtm3rm93kKgw0NOxt1McVBYX6m55oGxu1xxI&dib_tag=se&keywords=dc+motor+with+gearbox&qid=1715911706&sprefix=dc+motor+with+gearbox%2Caps%2C126&sr=8-4"> Link </a> |
| Multimeter | Measures current, resistance, and voltage to ensure safety | $9.99 | <a href="https://www.amazon.com/dp/B0CXM242J1?ref=fed_asin_title&th=1"> Link </a> |
| Red Ball | Object that the robot should track and go to | $16.73 | <a href="https://www.amazon.com/Champion-Sports-Inch-Coated-Density/dp/B000KYTTYO/ref=sr_1_2_sspa?dib=eyJ2IjoiMSJ9.TLCeZ2jjYwnvK3RiJf14C4RstYOZXhRWTRbHkmLGiNfm5Vd8mVjvtsbUnBFk0S4d6cW9cPT7XDdhwMcPC30nsNwer7Uim0JVF49R8Od82u3RH4TY4mO1uP5LtqdvIEcW7CaOm7AzQ6xOvWQ4say1Ci9eGOxETDRWJP5rewLnqARbrvbe4kh-b2d5NHCLEsarPl16pM1UVlmQCXfMRksXigf_GpckmWPjeUM1AC8iiU0.lGUWr3-ZcZJNl0nJ2JaU6JEUOF9oR26lf0kUvETdmtM&dib_tag=se&keywords=7+inch+red+ball&qid=1748284272&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1"> Link </a> |
| AA batteries | Powers the H-Bridge | $18.74 | <a href="https://www.amazon.com/Duracell-Coppertop-AA-Ingredients-Long-lasting/dp/B0035LCFNQ/ref=sr_1_2_sspa?crid=2YR65MVXWA50C&dib=eyJ2IjoiMSJ9.Y7LKJBX-6tZ05fw4EcW76nu14zklVu0uDSTwj-0-cV44GfYvoaYnLKVwcPIB1rWt_qVnpkZnwoqkvrQmMFQ1qiTWN_rokxCgCagwBWaAIiv9PAbMqrwOrkGuvfWfklSZi5Y9W6AaUUspAaSMBZuUyS4cUoJB-s35FE-4seDyYIxfOaNAZggr154hcf3CR015QRyanTdKe1P3g2-fihntxqYoU2ek7H01s8toH4MNd-E.Mnyne8z1KkhvfDMnfFLgjUB9WgjdkdMcYRL591Pngbk&dib_tag=se&keywords=aa+batteries&qid=1748284893&refinements=p_85%3A2470955011&refresh=1&rnid=2470954011&rps=1&sprefix=aa+batterie%2Caps%2C122&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1"> Link </a> |
| USB Power Bank | Powers the Rasberry Pi | $16.19 | <a href="https://www.amazon.com/SIXTHGU-Portable-Charger-Charging-Flashlight/dp/B0C7PHKKNK/ref=sr_1_2_sspa?crid=2ZZM4AAZMMWHQ&dib=eyJ2IjoiMSJ9.W2Zx5_I3mKOn6UpwAzOw6PD0PNh1iaMRBiedequdv9weeWL0HPyPcxJBR9h6-LiFW-sHKnHSApN0sUxx0Q9xIRs80R57IlvvCsmEzXcktogo-4nP-NxrEZOy5dJTcXY8N-PBwfGt4fl_9LP8npenzDUV9TPA8KN6DMu175g6JegC_gZhAJrbqX94EfpQhLwP9vIJH45w2N-AFrfZZOy9jqk55gzVyk4Qst8uZvqn768.KBrc5_SqZ4e8zCpoFc-1C7rk02t3o2ykgDPB65W5JJU&dib_tag=se&keywords=always%2Bon%2Bpower%2Bbank&qid=1715957917&sprefix=always%2Bon%2Bpower%2Bbank%2Caps%2C107&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1"> Link </a> |





# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
