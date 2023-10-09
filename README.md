*** Settings ***
Library           SeleniumLibrary

*** Test Cases ***
LoginToSonyLiv
    Open Browser    https://www.sonyliv.com    chrome
    Maximize Browser Window
    Sleep           2s    # Wait for the website to load

    # Click on the profile picture
    Click Element    xpath=//*[@class="profile-pic-container"]

    # Click on Sign-In menu item
    Click Element    xpath=//a[text()="Sign In"]

    # Validate if the "Sign in to continue" text appears
    Element Should Be Visible    xpath=//*[contains(text(), "Sign in to continue")]

    # Input your mobile number (replace with your actual mobile number)
    Input Text    xpath=//*[@name="mobile_number"]    YourMobileNumber

    # Add any additional steps here, e.g., entering the password and clicking the "Sign In" button

    # Close the browser
    Close Browser
