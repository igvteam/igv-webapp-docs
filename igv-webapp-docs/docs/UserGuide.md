
<!---
The page title should not go in the menu
-->
<p class="page-title"> User Guide </p>

# Quick Start

### 1. Open the IGV-Web app

In a [web browser](#supported-browsers), navigate to <https://igv.org/app>.   

!!! note " "
    Make sure that popups are not disabled in your web browser as some features rely on them. For example, loading tracks and genomes from files in Google Drive may pop up a login window. Also note that some options may not be available if all cookies have been disabled in the web browser preferences. 

### 2. Load a reference genome
IGV displays data mapped to the genomic coordinates of a reference genome. When the IGV-Web page first loads, it will load the default reference genome **hg19**. To load a different genome, click on the `Genome` dropdown menu and either select from the list of predefined genomes, or use one of the options to load a genome sequence file that you specify.

!!! note " "
    You must first load the reference genome, before loading data tracks. Switching genomes will clear out any loaded tracks.


#### Selecting a predefined genome

The available predefined genomes are listed in the menu. If you select any of these genomes, a corresponding gene annotation track will also be loaded.

!!! tip " "
    The menu includes the complete list of available predefined genomes. Unlike IGV-Desktop, there is no `More...` entry at the bottom of the menu to access a longer list.

#### Loading a genome sequence file

If you have an indexed FASTA file of your reference genome sequence, you can load it using one of the options in the top part of the menu: 

* `Local File`
* `Dropbox`
* `Google Drive`
* `URL`

Selecting the `URL` option will present a dialog where you enter the full web link URL to the FASTA file and to the corresponding index file. For the other options, both the FASTA file and the index file must be selected from the file chooser that pops up.

!!! note " "
    A FASTA file only has the sequence data and IGV cannot display the cytoband ideogram in the chromosome ruler or automatically load a corresponding gene annotation track. You can load a gene annotation file directly via the `Tracks` menu.

You will be prompted to sign into a Google account if you select the `Google Drive` option, and a [Dropbox](https://www.dropbox.com) account is needed for the `Dropbox` option. The `Google Drive` option will not be presented if cookies are disabled in the web browser.

!!! tip " "
    **Advanced:** Another option is to create and load a .json genome file, which can include references to a cytoband file and a default gene annotation track. See the [File Formats section](./FileFormats.md) for details on the IGV reference genome JSON format.

### 3. Load data tracks

To load data and genomic annotations, click on the `Tracks` dropdown menu and either select from the selection of predefined tracks or choose one of the options to load files that you specify.

#### Selecting a predefined track

Categories of available predefined tracks are listed in the menu. Clicking on a category will open a list of datasets. For example, if `ENCODE` is one of the menu items, clicking on it will bring up a list of datasets available from the ENCODE data portal (Encyclopedia of DNA Elements, <https://www.encodeproject.org>). 

!!! tip " "
    The set of predefined tracks presented in the menu varies depending on the current reference genome. Some genomes do not come with any predefined tracks. 

#### Loading a track file

To load track data from a file, use one of the options in the top part of the menu: 

* `Local File`
* `Dropbox`
* `Google Drive`
* `URL`

Selecting the `URL` option will present a dialog where you enter the full web link URL to one data file and the corresponding index file, if there is one. For the other options, a file chooser pops up and you can select files for multiple tracks, along with the corresponding index files. 

!!! note " "
    For indexed files, e.g. BAM files, you must explicitly select the index file along with the data file. If you also use IGV-Desktop, you may be used to IGV automatically finding and loading the index file. This is not always possible from a web browser, so the behavior is different in IGV-Web.

You will be prompted to sign into a Google account if you select the `Google Drive` option, and a [Dropbox](https://www.dropbox.com) account is needed for the `Dropbox` option. The `Google Drive` option will not be presented if cookies are disabled in the web browser.

The [File Formats section](./FileFormats.md) has information about supported file types.

!!! note " "
    Make sure to load only data files that correspond to the current reference genome. In general, a genomic data file does not include information about the genome it aligns to, which means IGV cannot automatically check if they match.

### 4. Navigate

IGV-Web provides several navigation controls for specifying the genomic region to view. A ruler indicating the extent of the current region is displayed below the toolbar, and the size of the region and its genomic coordinates are displayed in the toolbar.

* **Select a chromosome.** The chromosome dropdown menu in the toolbar includes an entry for every chromosome or contig in the current reference genome. Selecting a chromosome from the menu will set the view to include the whole chromosome. The ruler also includes a cytoband ideogram if you selected one of the predefined reference genomes.
![](./images/ToolbarRulerChr1_2.png)

* **Select chromosome "all"**. At the top of the list of chromosomes in the dropdown menu there is also the special entry `all` to view the whole genome, with all the chromosomes layed out side-by-side. Or you can enter `all` in the text box where the genomic coordinates are displayed.
![](./images/ToolbarRulerChrAll_2.png)   
	* Clicking on a chromosome in the whole-genome ruler will set the view to that chromosome, just like selecting the chromosome from the dropdown menu.

* **Enter genomic coordinates.** In the text box where the genomic coordinates are displayed, you can type the coordinates of the region you want to view (e.g. *chr17:41,195,312-41,278,500*). The thousands separator is optional, but the chromosome name is required. 

* **Search by gene name.** In the text box where the genomic coordinates are displayed, type the name of a gene (e.g. *BRCA1*) and hit return or click on the magnifying glass. IGV will look up the genomic coordinates for that gene and set the viewing region accordingly. *Currently supported for human and mouse genomes only.*

* **Enter multiple loci.** In the text box, you can enter multiple regions by gene name, genomic coordinates, or a mixture of the two, separated by spaces (e.g. *BRCA2 BRCA2 KRAS*). This will split up the IGV view into multiple panels and display the regions side-by-side, each with its own ruler. 
![](./images/ToolbarRulerMultilocus_2.png)   
	* Clicking on the genomic coordinates above the ruler of any of the panels will change the view to only that region.
	* Close a panel by clicking on the **X** on the right edge of its ruler.
 
* **Zoom and pan.** 
	* Use the zoom slider or the **+** and **-** buttons on the right end of the toolbar to zoom in and out. In multi-locus view, this will affect all the panels. *The zoom controls are not available in whole-genome view*.
	> **Note:** If your browser window is narrow, the **+** and **-** buttons appear without the slider widget.
	 
	* Double-click in any of the data tracks to zoom in one level. The new view will be centered on the point where you clicked.
	
	* Click and drag in the ruler to sweep out a region to zoom into.
	
	* Click on the cytoband ideogram to move the view to that locus without changing the zoom level.
	
	* In any of the data tracks, click and drag (left or right) to pan the view across the genome. 


# More about tracks

### Track attributes: gear menu
Clicking on a track's gear menu reveals a number of attributes. The set of attributes is determined by the type of file that was loaded into the track. For example, for a track displaying paired-end sequence alignments from a BAM file, the menu includes an option `View as pairs`. In addition to `Remove track`, all tracks will include the menu items `Set track name` and `Set track height`.

#### **Setting attributes on multiple tracks**
Clicking on the `Select Tracks` button in the toolbar displays checkboxes to the left of all the tracks. To set attributes for multiple tracks at once, select the tracks of interest by clicking in their checkboxes. The gear menus for those tracks will then contain only the attributes that can be applied to all of the selected tracks. For example, selecting `Set track color` in the gear menu of any of the selected tracks will set the color for all of them.

If you select multiple quantitative data tracks, you will see a new item `Group autoscale` in their gear menus, in addition to the `Autoscale` item that is always there for quantitative data tracks. 

* Autoscaling a single track will dynamically change the data range (Y-axis) of the track as you pan across the genome to maximize the display given the data currently in view and the track's height. 
* Group autoscaling will keep the data range of multiple tracks dynamically in sync.

### Track actions: popup menu
Right-clicking on a data track brings up a popup menu with actions you can perform. The set of menu items is determined by the type of file that was loaded into the track. For example, for a track displaying copy number data from a multi-sample SEG file, the menu includes an option `Sort by value`, which sorts the samples by copy number value at the locus where you clicked on the track. The sort order is toggled on each selection.

### Displaying track data details

Clicking on a data element in a track will display details about the element in a separate popup window. The type of details displayed depend on the track type. 

By default, when you click on the next data element, the previous popup will close. Use `Shift+click` to open multiple information popups.


### Moving and deleting tracks
When you load a track it will be added to the bottom of the IGV track panel. To change the track order, just click on the gray grab-bar on the right edge of the track and drag it up or down to the new location.

![](./images/Track.png){height=100}

To remove a track from the IGV browser, click on the gear icon to the right of the track and select `Remove track` from the menu that pops up. 

!!! note " "
    Removing a track does not just hide the track. If you want to show it again you must reload the data file.  

Loading a new reference genome will also delete all loaded data tracks. Refreshing the IGV-Web page in the browser will delete all loaded data and reset to the default reference genome. Or, if you launched IGV-Web from a shared URL or browser bookmark, refreshing the page will go back to the initial session state defined by the URL or bookmark. 

### Overlaying tracks

Quantitative data tracks can be combined so they are displayed together as overlaid charts in a single track. 

For example, the following two tracks:

![ ](../images/overlaytracks-before.png){width=600}

can be displayed as the following single track by multi-selecting the two tracks and then clicking on the `Overlay Tracks` button in the toolbar. 

![ ](../images/overlaytracks-after.png){width=600}

!!! tip " "
    To multi-select the tracks, first click on the `Select Tracks` button in the toolbar to display selection checkboxes to the left of all tracks, and then select the two tracks you want to overlay. 

Each chart is drawn with a default level of translucence so they don't completely obscure one another. Select `Set transparency` from the combined track's gear menu to make the charts more or less opaque.

To separate the charts into the original tracks, select `Separate tracks` from the combined track's gear menu.

!!! note " "
    You may want to set the data ranges to be the same on the tracks before overlaying them or you can enable autoscale in the gear menu of the combined overlay track to keep the data ranges of the constituate tracks in sync.




# Special tracks

### Sequence track

When zoomed in sufficiently, the reference genome sequence track appears just below the chromosome ruler. Depending on the zoom level, the sequence is represented by colored bars: 
![](./images/SequenceBlocks.png) 
or colored letters: 
![](./images/SequenceLetters.png)
with adenine (A) in green, cytosine (C) in blue, guanine (G) in yellow, and thymine (T) in red.

The gear menu for sequence tracks includes two options:

* **Strand direction.** Initially, the forward / positive strand is displayed. Click on `Reverse` to flip to the reverse / negative strand. Click on `Forward` to change it back.

* **Sequence translation.** Click on `Three-frame Translate` to display a 3-band track that shows a 3-frame translation of the amino acid sequence for the corresponding nucleotide sequence. The translation is shown for the current strand. Amino acids are displayed as blocks colored in alternating shades of gray. Methionines are colored green, and all stop codons are colored red. When you zoom all the way in, the amino acid symbols will appear. Click on `Close Translation` to collapse the track to display the sequence only.
![](./images/Sequence3FrameTranslate.png)

The sequence track cannot be removed, but it can be dragged to a different position, just like any other track.

### Gene annotation track

If you load a reference genome from the list of hosted genomes provided in the `Genome` menu, a special gene annotation track is also automatically loaded. For most of the hosted genomes, these annotations are from NCBI's Reference Sequence Database (RefSeq). You cannot remove this track, but it will be automatically unloaded if you select a different reference genome.

When you load a data track, it will be positioned just above this gene annotation track. So by default, the gene annotations are always displayed at the bottom. You can however move the gene annotation track at any time by dragging it to a different position, just like any other track. 

By default, the annotations are displayed in a compact mode, where overlapping transcripts are collapsed into a single line:
![](./images/GenesCollapsed.png)
The track gear menu provides two different options for expanding the display to show the overlapping features on separate lines: 
![](./images/GenesExpanded.png)
![](./images/GenesSquished.png)

!!! tip " "
    Changing the display mode does not affect the track height. A scrollbar will be added to the track if it is too short to display all the lines. To increase or decrease the track height, select `Set track height` from the gear menu.  

# Sample Attributes

For some multi-sample track types, such as segmented copy number (SEG files) and variant calls (VCF files), you can associated sample attributes with a track and use them for sorting the samples. 

* **To load and display sample attributes**, use the `Sample Info` menu to load a [sample attribute file](../FileFormats/#sample-info-attributes). 

The attributes are displayed as a matrix of colored blocks, where each column represents an attribute, and a row of blocks represets all the attribute values for a single sample. In IGV-Web the attribute matrix is displayed to the right of the track data and to the left of the track scroll bar (if there is one) and the track's gray grab bar.

![](./images/SampleAttributes.png)

If two samples have the same color block for a particular attribute, both samples have the same value for that attribute. However, the colors are arbitrary and different sessions of IGV may not use the same colors.

* Hover over any block in a colum to **display the attribute name**.

* Hover over a colored block to **display the attribute value** for a sample.
        
* Click in the gear menu and select one of the attribute names under `Sort by attribute:` to **sort the samples based on that attribute**.

* Click on the `Sample Info` button to **hide or show the sample attribute matrix**.

# Saving Sessions
IGV-Web has a number of options for saving the state of your IGV session: you can save a file in IGV session format, bookmark the page in your browser, or create a web link URL that you can share with others. 

Be aware that the saved state of an IGV session includes pointers to the data files for any loaded tracks. So to fully restore the state, you must have access to the same files that were loaded when the IGV session was saved.

!!! note " "
    Due to security restrictions on web browsers, if you loaded any files from the local file system, IGV cannot automatically load them for you when you restore the session **even if you run the session in the same environment on the same computer** where you saved the session. 


### Session files
To save a file that contains the state of the current IGV session, click on the `Session` dropdown menu, select `Save`, and enter a filename into the dialog that pops up. The filename must have the .json suffix, or it will not be recognized as a session file when later loaded into IGV-Web. Depending on your web browser settings, the file will be saved to your default downloads folder or you will be prompted to specify a destination folder. 

You can share your session with others, for example by emailing it to them, or copying the saved file to a shared file system, or uploading it to Dropbox, Google Drive, or a web server.

To restore a session from a saved file, click on the `Session` dropdown menu and select one of the options in the top part of the menu: 

* `Local File`
* `Dropbox`
* `Google Drive`
* `URL`

Selecting the `URL` option will present a dialog to enter the full web link URL to the session file. For the other options, a file chooser pops up. If you select the `Google Drive` option, you will be prompted to sign into a Google account, and a [Dropbox](https://www.dropbox.com) account is needed for the `Dropbox` option. The `Google Drive` option will not be presented if cookies are disabled in the web browser.

#### Session files from IGV-Desktop
Session files that were saved in the Java desktop version of IGV can also be loaded into IGV-Web via the `Session` dropdown menu. However, IGV-Desktop supports more features and file types than the IGV-Web app, and so the session may not be completely restored. Also note that session files saved in IGV-Web currently cannot be loaded into IGV-Desktop.

### Bookmarks
To bookmark the current state of the IGV page in your web browser, first click on `Bookmark` in the IGV-Web menu bar. This will update the URL in the web browser's address bar. Then you can use your browser to save a bookmark for the page (in most web browsers use `Command+D` on MacOS, `Ctrl+D` on Windows). 

To restore a bookmarked session, use your browser's mechanism for going back to a bookmarked page.

### Shareable links
To create a web link URL that will open the IGV-Web app with all the same data tracks and settings as the current session, click on `Share` in the menu bar. A dialog will pop up and display a short URL that encodes the current state of the IGV session.

* Use the `COPY` button to copy the URL to the clipboard and paste it wherever you want for safe keeping. 
* Alternatively, the `Tweet` and `EMAIL` buttons provide shortcuts for sending the URL to others. 
* The `EMBED` button generates an HTML code snippet that can be used to add the session to a web page. *Note: For the EMBED option, tracks loaded from Google Drive will only work if they are publicly available.*
* The `QR CODE` button generates a QR two-dimensional barcode for the URL.

To restore a session from a URL, paste it into a browser address bar, or click on the URL in an email message, tweet, etc.

# Saving Images

Two options are provided for saving images from the IGV-Web app: 

* Click on `Save SVG` in the app menu bar to create an image that includes all the data tracks as currently displayed, as well as the ruler and cytoband ideogram. The image file will be saved in SVG format, a scalable vector format that is useful for creating figures for publication. 
* You can save the image of an individual track via the track *popup menu*. Select SVG or PNG format. 

Depending on your web browser settings, the image files will be saved to your default downloads folder or you will be prompted to specify a destination folder. 


# Miscellaneous Tools

## Regions of Interest

*(Introduced in IGV-Web version 1.12.9)*

You can identify one or more genomic regions as special _Regions of Interest_. 

* To **create** a region of interest, hold down the Shift key and sweep out the region in the genome ruler. (Note: without the Shift key, sweeping out a region in the ruler will zoom in to that region). 

Regions of interest are visually indicated by a green bar below the ruler and a light gray area across all tracks, as shown in the screenshot below.

![](./images/RegionsOfInterest.png)

* To provide a **label or description** for a region of interest, click on the green bar and select `Set Description` from the popup menu and then enter the description.
* To **delete** a region of interest, click on the green bar and select `Delete Region` from the popup menu.

* To display a **table summary of all regions** of interest, click on the `ROI table` button in the toolbar. If you select a row in the table and click on the `Go To` button, the IGV browser will change the view to that region. Selecting multiple rows will set the view to a multi-locus view of all selected regions side by side.


## BLAT

*(Introduced in IGV-Web version 1.13.0)* 

IGV-Web supports [BLAT](http://en.wikipedia.org/wiki/BLAT_%28bioinformatics%29) (*BLAST-like Alignment Tool*) 
for on-the-fly alignment of query sequences from reads in alignment tracks. 

* Right-click on a read of interest in an alignment track (BAM or CRAM), and select `BLAT read sequence` from the popup menu. 
* If soft clips are displayed and are of sufficient length, the popup menu will also include options to BLAT the soft-clipped sequence. 

The sequence query is sent to an external BLAT search engine hosted at 
the [UCSC Genome Browser](https://genome.ucsc.edu/cgi-bin/hgBlat). UCSC's BLAT search supports most UCSC
derived genomes including human and mouse genomes. 


The results of a BLAT search are presented in two different ways:

* As a new **feature track** in the lower panel of IGV's display, where each feature in the track represents a hit; and
* As a **results table** that is displayed in a separate popup window. If you close the table window, you can open it again by selecting `Open table view` from the gear menu of the corresponding results feature track.

If you select a row in the results table and click on the `Go To` button, the IGV browser will change the view to that region. Selecting multiple rows will set the view to a multi-locus view of all selected regions side by side.
 

## Circular View
*(Introduced in IGV-Web version 1.9.0)* 

In collaboration with the JBrowse development team, we integrated the JBrowse 2 circular view component for exploring structural variants, chromatin interactions, and other long-distance interactions. Currently this integration supports structural variants from VCF files, paired-end and split-read alignments from BAM/CRAM files, and interaction pairs from bedPE and interact tracks. See [here](https://github.com/igvteam/igv-webapp/wiki/Circular-View) for more information about using the circular view with IGV-Web. The circular view will not be available if the web browser preferences have been set to disable all cookies.

# Help Menu

The `Help` dropdown menu provides links to:

* This online documentation.
* The IGV **user forum**, where you can post support questions, bug reports, feature requests and other suggestions.
* The **GitHub repository** that hosts the IGV-Web source code. It provides another means of reaching the IGV team for support (via Git issues), and it includes documentation on how to host a local installation of the IGV-Web app.
* IGV-Web version information.

# Supported Browsers

IGV-Web requires a modern web browser with support for JavaScript ECMAScript 2015. We try to test on the latest versions of Chrome, Safari, Firefox, and Edge. The Internet Explorer (IE) browser is not supported.

*GitHub Pages theme adapted from [mattgraham](https://twitter.com/mattgraham)* 
