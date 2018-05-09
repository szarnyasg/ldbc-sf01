# LDBC SF0.1 data set

Neo4j-ready CSV files for the [LDBC SNB](http://ldbcouncil.org/developer/snb), produced by its [DATAGEN](https://github.com/ldbc/ldbc_snb_datagen) component.

To load the data set, set the environment variables appropriately.

```console
export NEO4J_HOME=<todo>
export NEO4J_DB_DIR=<todo>

$NEO4J_HOME/bin/neo4j-import --into $NEO4J_DB_DIR \
  --id-type=INTEGER \
  --nodes:Message:Comment "comment_0_0.csv" \
  --nodes:Forum "forum_0_0.csv" \
  --nodes:Organisation "organisation_0_0.csv" \
  --nodes:Person "person_0_0.csv" \
  --nodes:Place "place_0_0.csv" \
  --nodes:Message:Post "post_0_0.csv" \
  --nodes:TagClass "tagclass_0_0.csv" \
  --nodes:Tag "tag_0_0.csv" \
  --relationships:HAS_CREATOR "comment_hasCreator_person_0_0.csv" \
  --relationships:IS_LOCATED_IN "comment_isLocatedIn_place_0_0.csv" \
  --relationships:REPLY_OF "comment_replyOf_comment_0_0.csv" \
  --relationships:REPLY_OF "comment_replyOf_post_0_0.csv" \
  --relationships:CONTAINER_OF "forum_containerOf_post_0_0.csv" \
  --relationships:HAS_MEMBER "forum_hasMember_person_0_0.csv" \
  --relationships:HAS_MODERATOR "forum_hasModerator_person_0_0.csv" \
  --relationships:HAS_TAG "forum_hasTag_tag_0_0.csv" \
  --relationships:HAS_INTEREST "person_hasInterest_tag_0_0.csv" \
  --relationships:IS_LOCATED_IN "person_isLocatedIn_place_0_0.csv" \
  --relationships:KNOWS "person_knows_person_0_0.csv" \
  --relationships:LIKES "person_likes_comment_0_0.csv" \
  --relationships:LIKES "person_likes_post_0_0.csv" \
  --relationships:IS_PART_OF "place_isPartOf_place_0_0.csv" \
  --relationships:HAS_CREATOR "post_hasCreator_person_0_0.csv" \
  --relationships:HAS_TAG "comment_hasTag_tag_0_0.csv" \
  --relationships:HAS_TAG "post_hasTag_tag_0_0.csv" \
  --relationships:IS_LOCATED_IN "post_isLocatedIn_place_0_0.csv" \
  --relationships:IS_SUBCLASS_OF "tagclass_isSubclassOf_tagclass_0_0.csv" \
  --relationships:HAS_TYPE "tag_hasType_tagclass_0_0.csv" \
  --relationships:STUDY_AT "person_studyAt_organisation_0_0.csv" \
  --relationships:WORK_AT "person_workAt_organisation_0_0.csv" \
  --relationships:IS_LOCATED_IN "organisation_isLocatedIn_place_0_0.csv" \
  --delimiter '|'
```
