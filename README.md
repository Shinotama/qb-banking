# qb-banking - Fleeca Bank CSS & HTML Update

# Own Licence

    Fleeca Bank CSS & HTML Update is a free update released by myself as a modification 
    to the work provided by the original qb-banking, I do not give permission for this
    modifications files to be distributed outside of this github, sold for profit or to
    be copied in full & re-released without prior communitcation with myself

# Original License

    QBCore Framework
    Copyright (C) 2021 Joshua Eger

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>

## Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-atms](https://github.com/qbcore-framework/qb-atms) - For using the local ATMs around the world
- [qb-logs](https://github.com/qbcore-framework/qb-logs) - For keeping records

# New and Updated CSS & Html overhaul 
## Screenshots
- Main Home Page with all current data

![image](https://user-images.githubusercontent.com/33585512/213752061-4b91a025-1710-448b-bf19-35c2940c4fe4.png)

- Account Options - Auto Updating card image, name, card number & signature

![image2](https://user-images.githubusercontent.com/33585512/213752153-620d433b-e6d2-492a-8ce1-4ff30bb550eb.png)

- Money Management - Shows all the money types & systems on one page, transfers waiting to be fixed by main QB-Banking.

![image3](https://user-images.githubusercontent.com/33585512/213752352-5763021d-16b1-4e09-9a31-3e21420c5d26.png)

- Current account statement with dark theme showing all details.

![image4](https://user-images.githubusercontent.com/33585512/213752460-4f25431c-d4db-42aa-b793-e7b2e6d2732e.png)

## Features
- Debit card Management (MasterCard/Visa) with PIN - Image for card with live updated numbers, name & signature.
- Savings Account - Using money management screen to deposit or withdraw money.
- Refreshed Detailed interface - CSS Overhaul with a GTA Fleeca Bank theme.
- /refreshBanks
- Business and Gang accounts
- Statements include ATM transactions (Pull request from QB-ATMS)

## Installation
### Manual
- Download the script and put it in the `[qb]` directory.
- Import `qb-banking.sql` in your database
- Add the following code to your server.cfg/resouces.cfg
```
ensure qb-core
ensure qb-logs
ensure qb-banking
ensure qb-atms
```
# Server.cfg Convar Update
- Global DrawTextUi Option
```
setr UseTarget false
``` 

- Global Target Option
```
setr UseTarget true
```

## Configuration
```
Config = {}

Config.Blip = {
    blipName = "Bank", -- Blips name for banks
    blipType = 108, -- Blip icon for banks
    blipColor = 37, -- Blip color for banks
    blipScale = 0.8 -- Blip scale for banks
    }

Config.ATMModels = { -- Props which will be considered as ATM (Can use /atm nearby)
        "prop_atm_01",
        "prop_atm_02",
        "prop_atm_03",
        "prop_fleeca_atm"
    }

Config.BankLocations = { -- Bank locations
    { ['x'] = 149.9,    ['y'] = -1040.46,   ['z'] = 29.37,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = 314.23,   ['y'] = -278.83,    ['z'] = 54.17,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = -350.8,   ['y'] = -49.57,     ['z'] = 49.04,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = -1213.0,  ['y'] = -330.39,    ['z'] = 37.79,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = -2962.71, ['y'] = 483.0,      ['z'] = 15.7,   ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = 1175.07,  ['y'] = 2706.41,    ['z'] = 38.09,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    { ['x'] = 1653.41,  ['y'] = 4850.6,     ['z'] = 41.99,  ['bankOpen'] = true, ['bankCooldown'] = 0 },
    
    -- Pacific Standard Bank
    { ['x'] = 246.64, ['y'] = 223.20, ['z'] = 106.29, ['bankOpen'] = true, ['bankCooldown'] = 0 },
    -- Paleto
    { ['x'] = -113.22, ['y'] = 6470.03, ['z'] = 31.63, ['bankOpen'] = true, ['bankCooldown'] = 0 },
}

Config.cardTypes = { "visa", "mastercard"} -- Debit card types (When requesting a debit card it gives randomly one of these.)
```
