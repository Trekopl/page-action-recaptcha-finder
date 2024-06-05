# page-action-recaptcha-finder
Find recaptcha pageAction parameter used on recaptcha v2 and recapcha v3

# How to Find the `pageAction` for reCaptcha v2 and v3

Understanding the `pageAction` parameter is essential for integrating reCaptcha v2 and v3 effectively. This guide will help you identify and use the `pageAction` parameter.

## Introduction to reCaptcha Versions

### reCaptcha v2 Variants
- **Normal**: The standard version where users solve a puzzle.
- **Enterprise**: An advanced, paid version with extra features for businesses.
- **Invisible**: Operates in the background with minimal user interaction.

### reCaptcha v3
- **Risk Analysis**: Uses a risk analysis engine to score user interactions, typically requiring no user interaction.

## What is `pageAction`?

`pageAction` is a parameter used in reCaptcha v3 for risk analysis. It represents the 'action' value, helping to assess the risk associated with different user actions on a page.

## Steps to Detect `pageAction`

### 1. Installation

#### Chrome Users
- Install the [Captcha Solver Auto Solve](https://chrome.google.com/webstore/detail/captcha-solver-auto-bypas/pgojnojmmhpofjgdmaebadhbocahppod) extension.

#### Firefox Users
- Install the [Captcha Solver Auto Solve](https://addons.mozilla.org/en-US/firefox/addon/capsolver-captcha-solver/) extension.

### 2. CapSolver Setup
- Visit [CapSolver](https://www.capsolver.com/).
- Press `F12` on your keyboard to open the developer tools.
- Go to the **CapSolver Captcha Detector** tab.

### 3. Detection
- Keep the CapSolver panel open and visit the website where you want to trigger the CAPTCHA.
- Trigger the CAPTCHA.
- **Do not close** the CapSolver panel before triggering the CAPTCHA.

## Identifying the `pageAction` Parameter

When using the CapSolver extension, it will detect various reCaptcha parameters, including `pageAction`. Follow these steps:

1. **Open Developer Tools**: Press `F12` to open the developer tools.
2. **Navigate to CapSolver Tab**: Select the **CapSolver Captcha Detector** tab.
3. **Trigger the CAPTCHA**: Perform the action on the website that triggers the reCaptcha.
4. **View Detected Parameters**: The CapSolver panel will display all detected parameters, including `pageAction`.

## Example JSON Output
After detection, CapSolver will provide a JSON with all relevant parameters, such as:

```json
{
  "clientKey": "YOUR_API_KEY",
  "task": {
    "type": "ReCaptchaV2TaskProxyless",
    "websiteURL": "",
    "websiteKey": "",
    "pageAction": "submit"
  }
}
```

## Conclusion

Detecting the `pageAction` parameter is straightforward with the CapSolver extension. This parameter is crucial for proper reCaptcha v3 integration and helps enhance your website's security by accurately assessing user interactions.

For more detailed information and advanced configurations, refer to the [CapSolver documentation](https://docs.capsolver.com/guide/captcha/ReCaptchaV2.html).
