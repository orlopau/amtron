**Get ChargeData**
----

Retrieves information how the wallbox charges the vehicle.

* **URL**

  /ChargeData?DevKey=:devKey

* **Method:**
  
  `GET`
  
*  **URL Params**

   **Required:**
 
   `devKey=[integer]`

* **Success Response:**
  
  * **Code:** 200 <br />
    **Datatypes:**
      * `EnumChargingState: [Idle, Charging, Paused, StandbyConnect, StandbyAuthorize, Terminated]`
    
    **Content:** 
    
    ```
    {
      "ChgState": [EnumChargingState],
      "Tariff": [string],      /* Current tariff */
      "Price": [number],       /* Price per kWh with current tariff in 0.1 cents per kWh */
      "Uid": [string],         /* UserId? */
      "ChgDuration": [number], /* how long the wallbox is charging the EV */
      "ChgNrg": [number],      /* how much energy the wallbox has charged in Wh */
      "NrgDemand": [number],   /* energy demand of the vehicle in Wh */
      "Solar": [number],       /* maybe percentage of solar energy for current charge */
      "EmTime": [number],      /* time in which the vehicle has to be fully charged, in Energy Manager mode in minutes*/
      "RemTime": [number],     /* time remaining of the set EmTime in minutes */
      "ActPwr": [number],      /* current power draw of vehicle */
      "ActCurr": [number],     /* currently set max. charging current per phase in A*/
      "MaxCurrT1": [number],   /* max current per phase in tariff1 */
      "BeginH_T1": [number],   /* ? */
      "BeginM_T1": [number],   /* ? */
      "PriceT1": [number],     /* Price per kWh with Tariff1 in 0.1 cents per kWh*/
      "MaxCurrT2": [number],   /* max current per pahse in tariff2 */
      "BeginH_T2": 22,
      "BeginM_T2": 0,
      "PriceT2": [number],     /* Price per kWh with Tariff2 in 0.1cents*/
      "RemoteCurr": [number],  /* current in A per phase as set by app control mode */
      "SolarPrice": [number],  /* price for solar energy in 0.1cents per kWh */  
      "ExcessNrg": [boolean],  /* if only excess energy should be used in energy manager mode */
      "TMaxCurrT1": [number],
      "TBeginH_T1": [number],   
      "TBeginM_T1": [number],  
      "TPriceT1": [number],
      "TMaxCurrT2": [number],
      "TBeginH_T2": [number],
      "TBeginM_T2": [number],
      "TPriceT2": [number],
      "TRemoteCurr": [number],
      "TSolarPrice": [number],
      "TExcessNrg": [boolean],
      "HCCP": [string]         /* ? */
    }
    ```
 
* **Error Response:**

  * **Code:** 403 FORBIDDEN

* **Notes:**

    * The **charging modes** here are named differently than in the ChargeApp.
    Remote is called App Control, Home Manager is Energy Manager and Time is Time control.
    * **Tariffs**: T1 - Main tariff, T2 - Off-peak tariff, T3 - Solar energy tariff
    * The objects prefixed with **T** have the same values as values without the prefix. 
    I'm not sure what purpose they serve.

