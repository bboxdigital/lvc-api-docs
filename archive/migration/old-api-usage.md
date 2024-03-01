# Old api usage

- ?command=get_locations
- ?command=get_events
- ?command=get_activities&start_date={date}&end_date={date}
- ?command=get_activitypublic&id={id}
- ?command=get_events&organisme=ville
- ?command=get_activitiespublic&maxcount=25&startindex=1&start_date=&end_date=2050-01-01&eventid=&discipline=&location=&sector=
- ?command=get_activity&id={id}
- ?command=get_sectors
- ?command=get_disciplines&disciplinesWebOnly=0
- command=get_activities&id={discipline_ID}&lang=fr&maxcount=75&startindex=1&last_minute_activities_only=0&organisme=
- command=get_activity&id={activity_ID}&lang=fr
- command=get_locations&lang=fr
- command=get_locationspublic&id={venue_ID}&lang=fr
- ?command=get_activities&lang={fr}&discipline={id}&sector={id}&maxcount=9999
- ?command=get_activity&lang={fr}&id={id}
- ?command=get_locations&lang={fr}&withShowing={0}
- ?command=get_disciplines&lang={fr}
- ?command=get_activities&lang={fr}&sectors={id}
- ?command=get_activitiespublic&lang={fr}
- ?command=get_activity&lang={fr}&id={id}
- ?command=get_activitypublic&lang={fr}&id={id}
- ?command=get_activitiespublic&sector_id={id}&lang={lang}&maxcount={limit}
- ?command=get_locationspublic&sector_id={id}&lang={lang}
- ?command=get_sectors&parentSector={id}
- ?command=get_sectors&parentSector={id}
- ?command=get_activitiespublic&maxcount=&lang=&sector=&discipline=&location=&start_date=&end_date=&startindex=
- ?command=get_activity&id=&lang=
- ?command=get_locations&lang=
- ?command=get_locationspublic&lang=&id=
- ?command=get_disciplines&lang=&disciplinesWebOnly=
- ?command=get_disciplines
- ?command=get_locationspublic&organisme={organisme}
- ?command=get_events&organisme=102
- ?command=get_activitiespublic&organisme={organisme}
- ?command=get_activitypublic&id={id}

## Events (query)
- ?command=get_events
- ?command=get_events&organisme=ville
- ?command=get_events&organisme=102

## Locations (query)
- ?command=get_locations
- ?command=get_locations&lang=fr
- ?command=get_locations&lang=
- ?command=get_locations&lang={fr}&withShowing={0}
- ?command=get_locationspublic&lang=&id=
- ?command=get_locationspublic&id={venue_ID}&lang=fr
- ?command=get_locationspublic&sector_id={id}&lang={lang}
- ?command=get_locationspublic&organisme={organisme}


## Sectors 
- ?command=get_sectors
- ?command=get_sectors&parentSector={id}
- ?command=get_sectors&parentSector={id}

## Activity -> ex: event page
- ?command=get_activity&id={id}
- ?command=get_activity&id={activity_ID}&lang=fr
- ?command=get_activity&lang={fr}&id={id}
- ?command=get_activity&lang={fr}&id={id}
- ?command=get_activity&id=&lang=
- ?command=get_activitypublic&id={id}
- ?command=get_activitypublic&lang={fr}&id={id}
- ?command=get_activitypublic&lang={fr}&id={id}
- ?command=get_activitypublic&id={id}

## Activities (query)
- ?command=get_activities&start_date={date}&end_date={date}
- ?command=get_activities&id={discipline_ID}&lang=fr&maxcount=75&startindex=1&last_minute_activities_only=0&organisme=
- ?command=get_activities&lang={fr}&discipline={id}&sector={id}&maxcount=9999
- ?command=get_activities&lang={fr}&sectors={id}
- ?command=get_activities&lang={fr}&id={id}
- ?command=get_activitiespublic&lang={fr}
- ?command=get_activitiespublic&organisme={organisme}
- ?command=get_activitiespublic&sector_id={id}&lang={lang}&maxcount={limit}
- ?command=get_activitiespublic&maxcount=&lang=&sector=&discipline=&location=&start_date=&end_date=&startindex=
?command=get_activitiespublic&maxcount=25&startindex=1&start_date=&end_date=2050-01-01&eventid=&discipline=&location=&sector=

## Disciplines (query)
- ?command=get_disciplines&lang=&disciplinesWebOnly=
- ?command=get_disciplines
- ?command=get_disciplines&lang={fr}
- ?command=get_disciplines&disciplinesWebOnly=0

