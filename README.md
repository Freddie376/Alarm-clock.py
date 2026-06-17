
import datetime
import time
import winsound 

def set_alarm(hour: int, minute: int, sound_file: str) -> None:
    while True:
        now = datetime.datetime.now()
        if now.hour == hour and now.minute == minute:
            print("Time to wake up!")
            winsound.PlaySound("alarm.wav", winsound.SND_FILENAME)
            break
        time.sleep(1)

if __name__ == "__main__":
    alarm_hour = int(input("Enter the hour (12-hour format):"))
    alarm_minute = int(input("Enter the minute:"))
    sound_file = "alarm.wav"
    print(f"Alarm set for {alarm_hour:02d}:{alarm_minute:02d}")
    set_alarm(alarm_hour, alarm_minute, sound_file)
