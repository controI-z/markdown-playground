# Collection Builder
1. Which fields are required for *all items* in CollectionBuilder-GH metadata

2. 

# Documentation Lab
## Instructions
In this lab, we'll practice reading documentation and looking for answers to our questions in the following documentation sources:
1. [CollectionBuilder documentation](https://collectionbuilder.github.io/cb-docs/)
2. [SUCHO documentation](https://wiki.sucho.org/en/tutorials/internet-archive/spreadsheet-metadata-template)
3. [Alex's TEI guidelines for archival transcription](https://alexandraewingate.com/projects/encoding-guidelines-for-initial-archival-tei-transcription/)

Answer the following questions using the documentation above. Turn in your completed Markdown file to the assignment on Canvas.
## Collection Builder
***For all answers in this section, give the answer and the URL of the page where you found it.***

1. **Which fields are required for *all items* in CollectionBuilder-GH metadata?**
* objectid
* filename
* title
* format

[location](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/#required-fields-for-collectionbuilder-gh)  

2. **What file do you need to edit to add a new page to your navigation bar?**

_data/config-nav.csv

[location](https://collectionbuilder.github.io/cb-docs/docs/pages/add_page/#add-a-new-page-to-the-nav)  

3. **What metadata fields are required to support the map visualization in CollectionBuilder-GH metadata?**
latitude & longitude
    
[location](https://collectionbuilder.github.io/cb-docs/docs/metadata/cdm_metadata/#fields-required-for-visualizations)  

4. **What four columns are included in the config-metadata.csv file?**
* Field
* display_name
* browse_link
* external_link

[location](https://collectionbuilder.github.io/cb-docs/docs/customization/config-metadata/#metadata--item-page-configuration-config-metadatacsv)  

5. **If you wanted a metadata field called "archive" in your metadata field to display as "Holding Institution" in the metadata section of each item's page, what file would you edit? (Bonus point: what columns of that file would you edit and what text would you input in each column?)**\
_data/config-metadata.csv

~~~ 
  field: archive
  display_name: Holding institution
~~~

[location](https://collectionbuilder.github.io/cb-docs/docs/customization/config-metadata/#metadata--item-page-configuration-config-metadatacsv)  

6. **How should the date September 8, 2023 be formatted so that the timeline visualization works?**

2023-9-8

[location](https://collectionbuilder.github.io/cb-docs/docs/metadata/cdm_metadata/#date)

7. **What column in what file allows you determine whether a field can be used for sorting on the Browse page of your website?**

sort_name in config-browse.csv

[location](https://collectionbuilder.github.io/cb-docs/docs/customization/config-browse/#sort_name)

8. **How do you change which metadata fields contribute values to the "Subjects" visualization page?**

subjects-fields

ex 
~~~
subjects-fields: subject;creator
~~~

[location](https://collectionbuilder.github.io/cb-docs/docs/theme/subjects/#subjects-page)

9. **What three items (keys) are in the YAML front matter of any of the markdown page files?**

layout
title
permalink

[location](https://collectionbuilder.github.io/cb-docs/docs/pages/basics/#yaml-front-matter)

10. **When filling in "metadata: " with the name of your metadata sheet on your "\_config.yml" file, should you include the file extension?**

no

[location](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/csv-walkthrough/#10-configure-your-site-settings-in-the-_configyml-file)

11. **Which file controls the display options for most of your website?**

_config.yml

[location](https://collectionbuilder.github.io/cb-docs/docs/config/site/#site-settings)

12. **How can you separate multiple values in a single field in your metadata file?**

use a semicolon

[location](https://collectionbuilder.github.io/cb-docs/docs/metadata/formatting/#formatting-your-metadata
)

13. **Find the example code for including a PDF from your collection (with a caption) on one of your interpretive pages (hint: start with the "Feature Includes" page)**

~~~
{% include feature/pdf.html objectid="demo_002" width="50" caption="a pdf from the collection" %}
~~~

[location](https://collectionbuilder.github.io/collectionbuilder-gh/feature_options.html)

## SUCHO Metadata
1. **Which metadata fields are always required for a SUCHO item?**

* columns a-e
* columns j,k,l,o

2. **What character separates multiple values in Column E and Column F?**

semicolon

3. **Format the name "Yevhen Federovych Stankovych" according to the content guidelines for Creator**

Yevhen, Federovych Stankovych

4. **What is the cardinality of the field "date?""**

high cardinality due to the large number of possible dates that include/exclude month and day

5. **What would be the correctly formatted value for the field "Host Location" for an item held by an institution in Lviv, the capital of Ukraine's Lviv Oblast?**

Lviv(Q360360)

6. **If you wanted to indicate that you were working on a row in our metadata spreadsheet, how would you do that?**

use column a


## Alex's TEI guidelines
1. **What tag should be used to indicate deleted text?**

~~~
<del>
~~~

2. **When should `<damage>` be used instead of `<gap>`?**

damage is used when there is damage but the text can still be read when confidence.
gap should be used when the text is completely illegible beyond recovery

3. **How would you indicate that a word is repeated in the following code block?**
```xml
<p>
The quick brown fox jumped over the the lazy dog.
</p>
```
<sic rend="repeated word"> the </sic>

4. **Which tag is used to enclose an entire list of non-book items and which tag is used to enclose a list of books? Which tag should be used to enclose an individual non-book item, and which tag should enclose an individual book item?**
use <list> for any non-book lists and <item> for any non book items.
use <listBibl> for any book lists and <bibl> for any book items
use <list> and <listBibl> as necessary for books/non-books (it's important to keep these two seperate for good data extraction)