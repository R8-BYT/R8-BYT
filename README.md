from datetime import datetime
import pytz
import random
import time

# Display banner with your name
def display_banner():
    banner = """
    ***********
    *                                     *
    *         Script By Zain Mods*
    *                                     *
    *******
    """
    print(banner)

# Call the banner function at the start
display_banner()

results = ["SMALL", "GREEN", "SMALL", "RED", "BIG", "GREEN", "BIG", "RED"]

while True:
    timezone = pytz.timezone("Asia/Kolkata")
    now = datetime.now(timezone)

    hours = now.hour
    minutes = now.minute

    total_minutes = (hours * 60) + minutes + 1

    total_minutes_formatted = "{:04d}".format(total_minutes)

    current_date = now.strftime("%Y%m%d")

    current_period = current_date + "01" + total_minutes_formatted

    period_type = random.choice(results)

    print("Current Period:", current_period, "(", period_type, ")")

    seconds_to_next_minute = 60 - now.second
    milliseconds_to_next_minute = seconds_to_next_minute * 1000

    time.sleep(milliseconds_to_next_minute / 1000)
