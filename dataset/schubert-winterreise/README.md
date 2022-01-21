# Schubert Winterreise Dataset

The content of this folder is related to the **[Schubert Winterreise Dataset](https://zenodo.org/record/3968389)**, as used for the Polifonia Project.
In particular, the folder contains the data from the original dataset (chord annotations and metadata), together with a set of metadata for each song in the dataset downloaded using different services ([Genius](https://genius.com/), [Secondhandsongs](https://secondhandsongs.com/), [Musicbrainz](https://musicbrainz.org/), [Songfacts](https://www.songfacts.com/), and [Spotify](https://spotify.com/)).

The repository is structured as follows:

- [chord_annotations](chord_annotations) contains the chord annotations (and their relative durations) of the original dataset. The annotations have been converted to JAMS format;
- [metadata](metadata) contains the metadata files of the original dataset;
- [cornucopia_data](cornucopia_data) contains additional metadata files downloaded using the cornucopia tool (currently still under development). This tool allows to retrieve and store metadata about each track of a music dataset from different web services, using web APIs. The format of the data stored in this folder follows the structure of the service from which the data was obtained;
- [data_map.csv](data_map.csv) contains a mapping between each track of the original dataset and the metadata stored in the folders documented above. The columns of this file link to the following data:
  - `artist`: contains the name of the artist;
  - `track_name`: contains the track name;
  - `genius/lyrics`: contains the name of the file containng the track's lyrics downloaded from Genius, that can be found in the [cornucopia_data/genius/lyrics](cornucopia_data/genius) folder (please note that for this dataset all the data in this folder are divided by artist name, i.e. 'Beatles' and 'Queen');
  - `genius/lyrics_annotation`: contains the name of the file containing the track's lyrics annotation (crowdsourced) downloaded from Genius, that can be found in the [cornucopia_data/genius/lyrics_annotation](cornucopia_data/genius) folder;
  - `musicbrainz/work_meta`: contains the name of the file containing the metadata of the track's composition downloaded from Musicbrainz (see Musicrainz's documentation for more detailed infrmation on their datamodel). These files ban be found in the [cornucopia_data/musicbrainz/work_meta](cornucopia_data/musicbrainz) folder;
  - `musicbrainz/recording_meta`: contains the name of the file containing the metadata of the track's recording downloaded from Musicbrainz (see Musicrainz's documentation for more detailed infrmation on their datamodel). These files ban be found in the [cornucopia_data/musicbrainz/recording_meta](cornucopia_data/musicbrainz) folder;
  - `musicbrainz/release_meta`: contains the name of the file containing the metadata of all the releases in which the track can be found, downloaded from Musicbrainz (see Musicrainz's documentation for more detailed infrmation on their datamodel). These files ban be found in the [cornucopia_data/musicbrainz/release_meta](cornucopia_data/musicbrainz) folder (please note that for this dataset all the data in this folder are divided by artist name, i.e. 'Beatles' and 'Queen'). The filename must be embedded with underscore-number before the `.json` extension: this is because a song can have more than one artist/performer and the information is stored in separate files (e.g. the filename release_e07d72b9-417c-4b98-8fb6-8446d5817162_1.json that can be found in the file `data_map.csv`, is not contained in the folder `cornucopia_data/musicbrainz/iso_queen_release_meta`, but there you will find release_e07d72b9-417c-4b98-8fb6-8446d5817162_1.json and release_e07d72b9-417c-4b98-8fb6-8446d5817162_2.json instead;
  - `musicbrainz/artist_meta`: contains the name of the file containing the metadata of the track's artist downloaded from Musicbrainz (see Musicrainz's documentation for more detailed infrmation on their datamodel. These files ban be found in the [cornucopia_data/musicbrainz/artist_meta](cornucopia_data/musicbrainz) folder (please note that for this dataset all the data in this folder are divided by artist name, i.e. 'Beatles' and 'Queen'). The filename must be embedded with underscore-number before the `.json` extension: this is because a track can be included in more than one release and the information is stored in separate files (e.g. the filename artist_e07d72b9-417c-4b98-8fb6-8446d5817162_1.json that can be found in the file `data_map.csv`, is not contained in the folder `cornucopia_data/musicbrainz/iso_queen_artist_meta`, but there you will find artist_e07d72b9-417c-4b98-8fb6-8446d5817162_1.json and artist_e07d72b9-417c-4b98-8fb6-8446d5817162_2.json instead;
  - `secondhandsong/artist_meta`: contains the name of the file containng the track's artist metadata downloaded from Secondhandsongs, that can be found in the [cornucopia_data/secondhandsongs/artist_meta](cornucopia_data/secondhandsongs) folder (please note that for this dataset all the data in this folder are divided by artist name, i.e. 'Beatles' and 'Queen')
  - `sonar_id`: contains the id used for the pourpose of the Sonar Demo (deprecated);
  - `chord_annotation_id`: contains the name of the file containing the chord annotation of the track. These files ban be found in the [cornucopia_data/chord_annotations](cornucopia_data/chord_annotations) folder.

The file contained in [cornucopia_data/songfacts](cornucopia_data/songfact) and [cornucopia_data/spotify](cornucopia_data/spotify) have **NOT** been aligned to the dataset, hence, you will not find any reference to them in the [data_map.csv](data_map.csv) file.

---