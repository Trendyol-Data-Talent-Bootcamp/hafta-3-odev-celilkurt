

```SQL

select 
          name, 
          c.id as car_id, 
          c.model as car_model, 
          m.year as manufacture_year,
          ARRAY(select as struct
                  p.id as id, 
                  TIMESTAMP_ADD( p.date, INTERVAL 3 HOUR) as date 
                from unnest(purchase) as p
                ) as purchase 
from  dsmbootcamp.abdulcelil_kurt.semi_structured_hw
join unnest(car) as c
join unnest(manufacture) as m
on c.id = m.id;



```
