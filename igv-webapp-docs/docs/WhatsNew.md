<!---
The page title should not go in the menu
-->
<p class="page-title"> What's New </p>

!!! Danger "Safari users:"
    If you see a blank page when clicking on the *Details* links on this page, try scrolling slightly to make the content appear.

<br>

**August 2024. IGV-Web 2.0.0 based in igv.js 3.0.1**

This is a major release with many new features, described below:


* Support for loading and displaying **sample attributes** for the samples in SEG and VCF files. The samples can also be sorted based on the attribute values. [Details...](../UserGuide/#sample-attributes) 

* **Alignment tracks:**

    * Group alignments by various attributes, for example, strand, pair orientation, tag, etc. Accessed via the track's gear menu.
    
    * Color by base modification as specified in MM and ML tags. Base modification options are added to the "Color by" section of the tracks' gear menu when those tags are present in the file. An example session that displays PacBio long-read sequencing data colored by base modifications is provided in the [Example Sessions](../ExampleSessions) section.
 	
	* Support for ambiguity codes in the read sequence.

	* Support for colors specified as hexadecimals in YC tags.

	* A new display mode: `Full` displays one alignment per row/line, which can be useful when viewing long-read sequencing data.
    
    * Previously both the coverage and alignments were always displayed. Now they can be hidden/shown separately via the track's gear menu.
 		

* **Variant (VCF) tracks:**

    * Sort by genotype via the track's right-click popup menu.
      
    * Color variants by: allele frequency (default); variant type; SV type; info field. Accessed via the tracks's gear menu.      
   
    * Variants that are marked as FAIL in the VCF file are drawn semi-transparent so they are visually apparent in the IGV view.
    
* **Quantitative data tracks:**

    * Autoscale groups of quantitative data tracks together. [Details...](../UserGuide/#setting-attributes-on-multiple-tracks)

    * Overlay two or more quantitative data tracks. [Details...](../UserGuide/#overlaying-tracks) 

    * When the view is zoomed out, each pixel on the screen may represent a genomic region that encompasses multiple numeric values in the data. A **windowing function** that specifies which of the multiple values to display can be selected in the gear menu. Choose between `mean` (default), `min`, and `max`. 

* **Genome annotations / feature tracks:**

    * When sufficiently zoomed in, amino acid sequences are displayed in exons.     

    * Navigate the view to the next or previous feature. [Details...](../UserGuide/#jump-to-nextprevious-feature)
 
* **Reference genome and sequence**

    * The GenBank (.gbk) file format is supported for the reference genome (sequence and default annotations).
    
    * The compact [UCSC twoBit format](https://genome.ucsc.edu/FAQ/FAQformat.html#format7) is supported for the reference genome sequence.  
    
    * The `Genome` menu includes an option to view a table of assemblies available at the UCSC GenArk site and select one to load into IGV. Other UCSC track hub genomes can be loaded via URL. [Details...](../UserGuide/#ucsc-genark)

    * The most recently used predefined genomes (up to 5 of them) are displayed above the full list of the available predefined genomes in the `Genome` menu. This feature works if third party cookies are enabled in your web browser.

    * Two new actions on regions of the reference sequence are available via `Regions of Interest`: (1) copy the sequence to the system clipboard; (2) BLAT the sequence. [Details...](../UserGuide/#regions-of-interest)

* **Misc**

    * Set attributes on multiple tracks at once. [Details...](../UserGuide/#track-attributes-gear-menu)
    
    * Display multiple information pop-ups with track data details. [Details...](../UserGuide/#displaying-track-data-details)
    
    * Support for *bedMethyl* files (format described on the [ENCODE site](https://www.encodeproject.org/data-standards/wgbs); scroll down the page to see the description).
    
    * New track type: *xQTL*. The [Example Sessions section](../ExampleSessions) has links a live IGV-Web app sessions that demonstrates xQTL tracks. 
    
    * Images can be saved in PNG format, as well as the SVG format that was already supported.
    
    * When the browser is too narrow to accommodate all the text buttons in the toolbar, they are replaced with smaller icon buttons. Hover over an icon to see the corresponding text. 
    
    * The `Help` menu *Documentation* item links to a new expanded documentation site at https://igv.org/doc/webapp. The menu also has a new item that directly links to a page on the documentation site with *Example Sessions*.
    

    

   




