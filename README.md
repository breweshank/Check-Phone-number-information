# Phone Number Information Lookup

## Overview
This Python script allows users to input any phone number (in international format) and retrieves detailed metadata associated with that number using the `phonenumbers` library. It is useful for:
- Identifying the region of a number
- Determining the telecom carrier
- Understanding which timezone(s) the number may be associated with

## Features
- **Interactive Input**: Accepts user input for the phone number.
- **Timezone Detection**: Displays the timezone(s) where the number is active.
- **Geographical Location**: Shows the likely region (e.g., state or country).
- **Carrier Lookup**: Identifies the mobile network or service provider.
- **Supports International Format**: Works globally with E.164 formatted numbers (e.g., +1 for USA, +91 for India).

## Requirements
Make sure Python 3 is installed. Then, install the required library:

### Install Dependencies
```sh
pip install phonenumbers
```

## Usage
### Step 1: Run the Script
Save the script as `phone_info.py` and run it using:
```sh
python phone_info.py
```

### Step 2: Input the Phone Number
You will be prompted to enter a number. Use international format with the `+` sign:
```
enter the number:- +14155552671
```

### Step 3: View the Output
The script will print:
```
timezone : ('America/Los_Angeles',)
location : California
Service provider : Verizon
```

## Sample Code
```python
import phonenumbers
from phonenumbers import timezone
from phonenumbers import geocoder
from phonenumbers import carrier

number = input("enter the number:- ")
phoneNumber = phonenumbers.parse(number)
timeZone = timezone.time_zones_for_number(phoneNumber)
print("timezone : "+str(timeZone))
x = geocoder.description_for_number(phoneNumber,"en")
print("location : " +x)
service = carrier.name_for_number(phoneNumber,"en")
print("Service provider : " +service)
```

## Notes
- This script only returns information based on the number prefix and does not reveal private subscriber information.
- Some numbers may not return all details if data is limited or unregistered.
- It is important to use the correct format when inputting the number.

## License
This project is licensed under the **MIT License**. Feel free to use, modify, and distribute with proper attribution.


