**Control energy manager mode**
----

Control the energy manager charging mode. All data can be found under ChargeData, there is no `GET` request
for HomeManager.

* **URL**

  /HomeManager?DevKey=:devKey

* **Method:**
  
  `POST`
  
*  **URL Params**

   **Required:**
 
   `devKey=[integer]`

* **Data Params** <br />

  Solar price can be set to null when no changes have to be made.
    
  ```
  {
  	"Permanent": [boolean],           /* if changes made here are saved permanently */
  	"NrgDemand": [number],            /* how many Wh should be charged */
  	"ExcessNrg": [boolean],           /* true if charging should only take place when there is excess solar energy */
  	"SolarPrice": [number],           /* solar energy price in 0.1 cents per kWh */
  	"RemTime": [string]               /* time in which the vehicle has to be fully charged in minutes */
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
  	"Permanent": false,
  	"NrgDemand": 15000,
  	"ExcessNrg": false,
  	"SolarPrice": null,
  	"RemTime": 1250
  }
  ```

* **Notes:**

    RemTime is always calculated since the point in time when the vehicle was plugged in to the wallbox.
    The same is true for the NrgDemand. Even if some energy was already consumed by the vehicle, the energy here
    is calculated from the beginning.
    
    For example, if you already charged your car for 60min, consuming 10kWh, you can set `"RemTime": 120` to charge
    for another 60 minutes. If you want to charge another 5kWh, set `"NrgDemand": 15000`.

