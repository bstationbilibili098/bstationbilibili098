name: Windows - Anydesk RDP



on:

  workflow_dispatch:



jobs:

  build:

    name: Built Connection

    runs-on: windows-latest

    timeout-minutes: 9999

    

    steps:

      - name: Downloading & Installing Essentials

        run: |

          Invoke-WebRequest -Uri "https://www.dropbox.com/s/ei73gt7vevxck2t/Downloads.bat?dl=1" -OutFile "Downloads.bat"

          cmd /c Downloads.bat



      - name: Log In To AnyDesk

        run: cmd /c start.bat



      - name: Time Counter

        run: Start-Sleep -Seconds 21600
