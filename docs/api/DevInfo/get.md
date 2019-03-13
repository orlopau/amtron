**Get DeviceInfo**
----

Retrieves information about the wallbox.

* **URL**

  /DevInfo?DevKey=:devKey

* **Method:**
  
  `GET`
  
*  **URL Params**

   **Required:**
 
   `devKey=[integer]`

* **Success Response:**
  
  * **Code:** 200 <br />
    **Datatypes:**
      * `EnumDevMode: [Remote, HomeManager, Time]` <br/>
      * `EnumChargingState: [Idle, Charging, Paused, StandbyConnect, StandbyAuthorize]`
    
    **Content:** 
    
    ```
    {
      "DevName": [string],        /* Name of the device */
      "LocTime": [number],        /* timestamp */
      "Summer": [boolean],        /* Is summer time? */
      "Tz": [number],             /* timezone offset in minutes */
      "ItemNo": [string],         /* item number */
      "Sn": [number],             /* Serial Number */
      "Hcc3": [string],           /* Info about the HCC3 (main controller) */
      "Hmi": [string],            /* Info about hardware software? */
      "Rfid": [string],           /* Info about RFID? */
      "Wifi": [string],           /* WiFi module version? */
      "FixedVehCosts": [number],  /* Fixed vehicle costs as specified in the app */
      "OldVehCosts": [number],    /* OldVehicle costs? */
      "Color": [number],          /* ? */
      "DevMode": [EnumDevMode],   /* Curent charging mode */
      "ChgState": [EnumChargingState], /* Current charging state */
      "WifiOn": [boolean],        /* true if WiFi is on */
      "AutoChg": [boolean],       /* true if auto-start charging is enabled*/
      "ChgContinue": [boolean],   /* true if charging should continue after power outage */
      "Err": [number],            /* current error code, 0 if there is none */
      "Battery": [number],        /* EV battery capacity for EnergyManager in Wh*/
      "Phases": [number],         /* number of phases connected */
      "Cable": [boolean],         /* true if cable is connected/installed? */
      "Auth": [boolean],          /* true if auth by rfid is enabled? */
      "DsoEnabled": [boolean],    /* ? */
      "EmEnabled": [boolean],     /* true if EnergyManager mode is enabled */
      "MaxCurr": [number],        /* currently set max. charging current per phase in A*/
      "MaxPwr": [number],         /* currently set max. charging power in W*/
      "MaxCurrWb": [number]       /* upper limit for charging current per phase in A*/
    }
    ```
 
* **Error Response:**

  * **Code:** 403 FORBIDDEN

* **Notes:**

    The charging modes here are named differently than in the ChargeApp.
    Remote is called App Control, Home Manager is Energy Manager and Time is Time control.

