# Xenia Pipelines

Durations: [day|week|month]* 
Targets: [user|asset|section|author]

__note__: hour was removed due to lack of nytimes data specificity.  After optimizaitons are made, we will decide upon the most usable duration scheme.

## Timeseries

Total activity over a time period

```
http://10.0.1.84:4000/1.0/exec/comment_timeseries_iso?start=2013-01-01&end=2013-02-01&duration=week&target=totals
```



### By user

Gives the lifetime activity of a user by duration

```
http://10.0.1.84:4000/1.0/exec/entity_comment_timeseries_iso?duration=month&target=user&id=567ab3dee19ac85217334fc2
```

### By asset

Gives the lifetime activity on an asset by duration

```
http://10.0.1.84:4000/1.0/exec/entity_comment_timeseries_iso?duration=month&target=asset&id=567ab3dee19ac85217334fc2
```

### By section / author (coming soon)



## Entity based data

### Users

No pipelines have yet been written, but the user table is now contains significant amounts of information:

```
{ 
    "_id" : ObjectId("567ab3dfe19ac85217335069"), 
    "src_id" : "46920789", 
    "user_name" : "suejean", 
    "avatar" : "", 
    "status" : "", 
    "stats" : {
        "comments" : {  // comment activity broken down by moderation status
            "accepted" : NumberInt(2925), 
            "rejected" : NumberInt(9), 
            "total" : NumberInt(2934)
        }, 
        "sections" : { // sections commented in
            "Crosswords & Games" : NumberInt(2909), 
            "Opinion" : NumberInt(1)
        }, 
        "authors" : { // authors commented on
            "Patrick Merrell" : NumberInt(76), 
            "Jim Horne" : NumberInt(71), 
            "Deb Amlen" : NumberInt(2656), 
            "Thomas Gaffney" : NumberInt(103), 
            "Margaret Sullivan" : NumberInt(1), 
            "The New York Times" : NumberInt(1), 
            "Will Shortz" : NumberInt(2)
        }, 
        "accept_ratio" : 0.9969325065612793, // accepted comments / total comments
        "replies" : NumberInt(2412),  // replies to this user
        "replies_per_comment" : 0.8220859169960022 
    }
}
```

You will need to add indexes manually until xenia supports index dependencies.  Do so here: [indexes.md](indexes.md)
