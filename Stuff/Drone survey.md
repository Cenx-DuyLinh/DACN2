---
type: Report
---
# Overall Comparison
---
```dataview
table Manufacturer,Configuration,Engine-number,MTOW,Payload, Fuel-type, Endurance, Service-ceiling, Cruise-speed, Wingspan as "Wingspan[m]", Lenght as "Lenght[m]", Payload,Comunication-type,Comunication-range, Price
where project = "drone survey"

sort name asc
```

# Sorted by MTOW
---
```dataview 
table 
manufacturer, MTOW as "MTOW[kg]"
where project = "drone survey"
sort mtow asc
```

# Sorted by Wingspan 
---
```dataview 
table 
Cruise-speed, Wingspan as "Wingspan[m]"
where project = "drone survey"
sort wingspan asc
```

# Sorted by Vũ
---
```dataview 
table 
payload, Wingspan, MTOW
where project = "drone survey"
sort wingspan asc
```

