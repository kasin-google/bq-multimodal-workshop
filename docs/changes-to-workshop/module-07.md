Change all
```
SET @@location='us-central1';
```
Into 
```
SET @@location='asia-southeast3';
```

```
SET @@location='asia-southeast3';
SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://<<PROJECT_ID>>-petverse/yoda_profile_picture.png', 'projects/<<PROJECT_ID>>/locations/us-central1/connections/pet-connection'))
```

```
SELECT name,
AI.GENERATE(
   prompt=> ('What are this pet\'s favorite toy and favorite foods', additional_media ),
    connection_id => 'asia-southeast3.pet-connection',
    endpoint => 'https://aiplatform.googleapis.com/v1/projects/affable-album-486805/locations/global/publishers/google/models/gemini-2.5-flash',
output_schema => 'food STRING, toy STRING')
FROM petverse.pets
WHERE name = 'Rocky'

```

or if you would like to try Gemini 3 Flash Preview
```
SELECT name,
AI.GENERATE(
   prompt=> ('What are this pet\'s favorite toy and favorite foods', additional_media ),
    connection_id => 'asia-southeast3.pet-connection',
    endpoint => 'https://aiplatform.googleapis.com/v1/projects/affable-album-486805/locations/global/publishers/google/models/gemini-3-flash-preview',
output_schema => 'food STRING, toy STRING')
FROM petverse.pets
WHERE name = 'Rocky'
```

```
UPDATE petverse.pets AS p
SET FavoriteFood = aigen.food
FROM
  (
    SELECT Id, name,
          AI.GENERATE(
                prompt=> ('What are this pet\'s favorite toy and favorite foods', additional_media ),
                connection_id => 'asia-southeast3.pet-connection',
                endpoint => 'https://aiplatform.googleapis.com/v1/projects/affable-album-486805/locations/global/publishers/google/models/gemini-2.5-flash',
                output_schema => 'food STRING').food
    FROM petverse.pets ) AS  aigen
WHERE p.Id = aigen.Id
AND p.FavoriteFood IS NULL
AND p.additional_media IS NOT NULL

```

```
ALTER TABLE petverse.pets ADD COLUMN MediaDescription STRING;
UPDATE petverse.pets AS p
SET MediaDescription = aigen.description
FROM
  (
    SELECT Id, name,
          AI.GENERATE(
                prompt=> ('Create a description in an epic tone for this pet based on these media: ', additional_media ),
                connection_id => 'asia-southeast3.pet-connection',
                endpoint => 'https://aiplatform.googleapis.com/v1/projects/affable-album-486805/locations/global/publishers/google/models/gemini-2.5-flash',
                output_schema => 'description STRING').description
    FROM petverse.pets ) AS  aigen
WHERE p.Id = aigen.Id
AND p.MediaDescription IS NULL
AND p.additional_media IS NOT NULL
```