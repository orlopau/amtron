**Set DevInfo**
----

Sets new device info, for example the current charging mode.

* **URL**

  /DevInfo?DevKey=:devKey

* **Method:**
  
  `POST`
  
*  **URL Params**

   **Required:**
 
   `devKey=[integer]`

* **Data Params** <br />

  **Datatypes:**
    * `EnumDevMode: [Remote, HomeManager, Time]`<br />

  All parameters can be set to null if no change is intended.
    
  ```
  {
    "DevName": [string],        /* device name */
    "LocTime": [string],        /* timestamp */
    "Summer": [boolean],        /* summer time */
    "Tz": [number],             /* timezone offset in minutes */
    "FixedVehCosts": [number],  /* Fixed vehicle costs as specified in the app */
    "OldVehCosts": [number],    /* OldVehicle costs? */
    "Battery": [number],        /* EV battery capacity for EnergyManager in Wh*/
    "DevMode": [EnumDevMode]    /* Charging mode */
  }
  ```

* **Success Response:**
  
  * **Code:** 200
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED

  OR

  * **Code:** 400 BAD REQUEST

* **Sample Data Params:**

  ```json
  {
    "DevName": null,
    "LocTime": null,
    "Summer": null,
    "Tz": null,
    "FixedVehCosts": null,
    "OldVehCosts": null,
    "Battery": null,
    "DevMode": "Remote"
  }
  ```

* **Notes:**

    The charging modes here are named differently than in the ChargeApp.
    Remote is called App Control, Home Manager is Energy Manager and Time is Time control.
