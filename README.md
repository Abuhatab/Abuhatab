- import pyautogui

def toggle_window_size():
    current_window = pyautogui.getActiveWindow()
    if current_window.maximize():
        current_window.minimize()
    else:
        current_window.maximize()

def follow_mouse():
    mouse_x, mouse_y = pyautogui.position()
    pyautogui.moveTo(mouse_x, mouse_y, duration=0.1, tween=pyautogui.easeInOutQuad)

def main():
    while True:
        # Press "Z" to toggle window size
        if pyautogui.hotkey('z'):
            toggle_window_size()
        # Press "F" to follow mouse
        elif pyautogui.hotkey('f'):
            follow_mouse()

if __name__ == '__main__':
    main()
