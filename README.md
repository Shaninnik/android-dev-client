## To use this repo

You will need to finish configuring expo updates to use your EAS account/project. Set `extre.eas.projectId` and `updates.url` in `app.json`

## Steps I took to reproduce the error

1. Created a project with `expo init`
2. Ran `expo install expo-dev-client`
3. Ran `expo install expo-updates`
4. Ran `eas build:configure`
5. Ran `eas update:configure`
6. Ran `eas build --profile development --platform android`, or `eas build --profile development --platform android --local` to build locally (faster) and install .apk on emulator or device
7. Ran `eas update --channel development ` to generate new update
8. Ran the build on emulator or device, toggle dev client, navigate to Extensions tab and verified that I can see regular Login/Signup UI. Logged in with my account and verified that I can see regular EAS Update UI and am able to install the update.
9. Deleted the application, changed `newArchEnabled` to `false` in `app.json` ran and installed build again
10. Ran the build on emulator or device, toggle dev client, navigate to Extensions tab and instead of regular UI only empty screen is visible. Logged in using "profile" button on top right, EAS Update UI is not visible
11. Tried installing update using update URL copied from Expo dashboard which resulted in "There was a problem loading the project", "Failed to open app".