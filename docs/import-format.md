Model import format specification
=================================

Format version: 1

File contents for upload with makebundle.sh
-------------

In order to import an model files into the site, the file needs to be in a ZIP compressed file containing:

all .STL/.OBJ files must be without errors!

* manifest.json                - A JSON document that defines the metadata for the model. See below
* solid.stl                    - print solid in resolution suited for printing.
* surface-orig.stl             - original resolution surface, for archival purposes.
* surface-medium.stl           - A surface in correct orientation, viewable on a larger screen such as a desktop.
* surface-low.stl              - A surface in correct orientation, viewable on a mobile phone or tablet.
* screenshot.jpg               - A screenshot of the model as shown on the site, suitable for previewing the model
                               

File contents for upload with sevolop.sh
-------------

In order to import an model files into the site, the file needs to be in a ZIP compressed file containing:

all .STL/.OBJ files must be without errors!

* manifest.json                - A JSON document that defines the metadata for the model. See below
* solid.stl                    - print solid in resolution suited for printing.
* surface-orig.stl             - original resolution surface, for archival purposes.
* screenshot.jpg               - A screenshot of the model as shown on the site, suitable for previewing the model



manifest.json
-------------

The manifest.json file should be a valid JSON document that contains the 
following keys:

```json
{
    "version":        1,
    "id":             "<model ID>",
    "created":        "2019-05",
    "released":       "2019-07-09",
    "gender":         "female",
    "gender_comment": "",
    "country":        "ES",
    "age":            34,
    "body_type":      "thin",
    "body_part":      "bust",
    "arrangement":  	"spread",
    "excited":  	    "not excited",
    "pose":           "lying",
    "mother":         "vaginal",
    "ethnicity":      "of Carribean descent",
    "tags":           ["#post-pregnancy"],
    "modification":   ["pregnancy", "breastfed"],
    "comment":        "Model was breastfeeding at the time.",       
    "other":          {}
}
```

id
--

The unique ID of the model

created
-------

A partial ISO 8601 timestamp of when model was created: YYYY-MM


released
--------

An ISO 8601 date of when model was released to on the we are beautiful site: YYYY-MM-DD


gender
------

| Allowable values |
| --------- |
| female |
| male |
| trans-mtf |
| trans-ftm |
| other |

If other is given for gender, a command giving more information must be present in
the "gender_comment" field.

country
-------

A two character ISO country code

age
---

Age in years of the model when model was created.


ethnicity
---------

This is a free form text field that the model should self declare. There is no existing taxonomy that handles
this well on a global scale. 


body_type
---------

| Allowable values |
| --------- |
| thin |
| fit |
| full |
| overweight |


bodypart
--------

Allowable values and their short cut codes:

| short| full text |
|------|---------|
| Y    |body |
| B    |breast |
| S    |bust |
| U    |buttocks |
| N    |nipple |
| P    |penis |
| T    |torso |
| V    |vulva |


excited 
-------

Allowable values and their short cut codes:

| short|full text |
|------|---------|
| N    |not excited |
| X    |excited |
| P    |partially excited |


arrangement
-----------

Allowable values and their short cut codes:

| short|full text |
|------|---------|
| S    |spread (have the vulva lips been spread apart?) |
| R    |retracted (is the foreskin retracted?) |
| A    |arranged (arrange in a fashion to illustrate a body feature) |
| N    |natural (as it appears when becoming unclothed) |


pose
----

Allowable values and their short cut codes:

| short|full text |
|------|---------|
| S    |standing |
| T    |sitting |
| L    |lying |


mother
------

Is the model a mother? If so, how was/were the child/children delivered?

| Allowable values |
| --------- |
| not |
| vaginal |
| caesarean |


modification
------------

Indicates modification of the model. One of more of the following may be allowed:

| Allowable values |
| --------- |
| pregnancy |
| nursed |
| circumcised |
| augmented |
| episiotomy |
| mastectomy  |
| labiaplasty |
| female-to-male |
| male-to-female |
| fgm |
| orchiectomy | 


tags
----

An array of tags (without hashes) that may also apply to this model.

"#small-areola #piercing" would be expressed in JSON as:

 `["<size>-<body_sub_part>", "<description>"]`  

| tag-building blocks| common values  |
|---------------------------|----------------|
| size:                     | small, large,    |
| body_sub_part:            | inner-labia, penis, brests, areola, scrotum, buttocks, clitoris |

| Allowable values for descriptions|
| --------- |
| asymetric-labia, asymetric-breast, bent-penis, inverted-nipple, piercing, bodymodification (decorative cutting, branding, scarring), |



comment
-------

General comment about the model not captured in other metadata. Free form text.


other
-----

Free form dictionary for custom data fields -- these fields may be accepted as full fiels in the future.

