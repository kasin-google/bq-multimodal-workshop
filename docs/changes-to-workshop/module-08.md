```
SET @@location='asia-southeast3';

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/yoda_profile_picture.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/Yoda_asks_for_cuddles.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 1;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/madonna_profile_picture.jpg', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/Madonna_description.wav', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 2;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/pixel_profile_picture.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/pixel_thug_life.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
                       (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/pixel_description.wav', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 3;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/sql_profile_picture.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/SQL_description.wav', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
                       (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/SQL_favorite_toy.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 4;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/buddy_golden_retriever.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = NULL
WHERE Id = 5;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/daisy_french_bulldog.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = NULL
WHERE Id = 6;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/max_german_shepherd.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/max_description_tells_jokes.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 7;

UPDATE petverse.pets SET profile_picture = NULL, additional_media = NULL WHERE Id = 8;

UPDATE petverse.pets SET profile_picture = NULL, additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/rocky_description.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))] WHERE Id = 9;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/pip_hamster.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/pip_Hamster_Wheel_Video_Generated.mp4', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 10;

UPDATE petverse.pets SET profile_picture = NULL, additional_media = NULL WHERE Id = 11;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/scales_snake.png', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = NULL
WHERE Id = 12;

UPDATE petverse.pets SET profile_picture = NULL, additional_media = NULL WHERE Id = 13;

UPDATE petverse.pets
SET profile_picture = (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/Joel_Profile_Picture.jpg', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
    additional_media = [(SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/Joel_Catwalk.jpg', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
                       (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/Joel_Flowers.jpg', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection'))),
                       (SELECT OBJ.FETCH_METADATA(OBJ.MAKE_REF('gs://th-region-bq-multimodal-app-petverse/additional_media/Joel_Plays.jpg', 'projects/th-region-bq-multimodal-app/locations/asia-southeast3/connections/pet-connection')))]
WHERE Id = 14;
```