## GTFS-ride Style Guide

The GTFS-ride specification follows largely the guide of GTFS. As such, the guidance for style shall be the same.
Retrieved from: [https://github.com/google/transit/blob/master/gtfs/spec/en/style-guide.md](https://github.com/google/transit/blob/master/gtfs/spec/en/style-guide.md)


>### Route Organization
>
>The entries in [routes.txt](https://github.com/google/transit/blob/master/gtfs/spec/en/reference.md#routestxt) should typically have the same organization as the physical routes communicated to riders by an agency. As an example, an agency will often first group their timetables by route when presenting them on a website or in a printed booklet. The entries in routes.txt should generally have a one-to-one correspondence to the timetable routes. It can be tempting for an agency to break a physical route into multiple entries in routes.txt in order to represent different route variations, such as direction of travel, but the preferred approach is to instead use features of [trips.txt](https://github.com/google/transit/blob/master/gtfs/spec/en/reference.md#tripstxt) to model those variations. Multiple entries in routes.txt with the same route short name or route long name are often an indication that routes have been needlessly subdivided.
>
>Do:
>
>~~~
>**routes.txt**
>route_id,route_short_name,route_long_name,route_type
>R10,10,Airport - Downtown,3
>~~~
>
>~~~
>**trips.txt**
>route_id,trip_id,trip_headsign,direction_id
>R10,T-10-1,Airport,0
>R10,T-10-2,Downtown,1
>~~~
>
>Don't:
>
>~~~
>**routes.txt**
>route_id,route_short_name,route_long_name,route_type
>R10-in,10,To Downtown,3
>R10-out,10,To Airport,3
>R20-in,20,To Downtown,3
>R20-out,20,To University,3
>~~~
