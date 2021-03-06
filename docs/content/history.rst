#############################
Release History
#############################

0.6.3 (in development)
=======================================
1. Addition permutation testing to the c-alpha test via the ``--permutations`` option.
2. Addition of the ``--passonly`` option during loading to filter out all variants with a filter flag set.
3. Fixed bug with parallel loading using the extended sample table format.
4. SLURM support added.

0.6.2 (2013-Oct-7)
=======================================
1. Moved `--tped` and `--json` options into the more generic `--format` option.
2. Fixed bug in handling missing phenotypes in the sample table.
3. Fixed `--tped` output formatting error.
4. API change: GeminiQuery.run takes an optional list of predicates that a row must pass to be returned.
5. `--sample-filter` option added to allow for restricting variants to samples that pass the given sample query.
6. ethnicity removed as a default PED field.
7. PED file format extended to allow for extra columns to be added to the samples table under the column named in the header.
8. The autosomal_recessive and autosomal_dominant tools now warn, but allow for variants to be detected in the absence of known parent/child relationships.


0.6.1 (2013-Sep-09)
=======================================
1. Corrected bug in de_novo tool that was undetected in 0.6.0.  Unit tests have been added to head this off in the future. Thanks to **Jessica Chong**
2. Added the `-d` option (minimum sequence depth allowed for a genotype) to the `autosmal_recessive` and `autosmal_dominant` tools.
3. New `--tped` option in the `query` tool for reporting variants in TPED format. Thanks to **Rory Kirchner**.
4. New `--tfam` option in the `dump` tool for reporting sample infor in TFAM format. Thanks to **Rory Kirchner**.



0.6.0 (2013-Sep-02)
=======================================
1. Add the ``--min-kindreds`` option to the ``autosomal_recessive`` and ``autosomal_dominant`` tools to restrict candidate variants/genes to those affecting at least ``--min-kindreds``. Thanks to **Jessica Chong**
2. Addition of a new ``burden`` tool for gene or region based burden tests.  First release supports the C-alpha test.  Thanks to **Rory Kirchner**.
3. Use of Continuum Analytics Anaconda python package for the automated installer. Thanks to **Brad Chapman**.
4. Enhancements to the ``annotate`` tool allowing one to create new database columns from values in custom BED+ annotation files.  Thanks to **Jessica Chong** and **Graham Ritchie**.
5. Addition of the ``--column``, ``--filter``, and ``--json`` options to the ``region`` tool.
6. Improvements to unit tests.
7. Allow alternate sample delimiters in the ``query`` tool via the ``--sample-delim`` option.  Thanks to **Jessica Chong**.
8. Provide a REST-like interface to the gemini browser.  In support of future visualization tools.
9. Allow the ``query`` tool to report results in JSON format via the ``--json`` option.
10. Various minor improvements and bug fixes.




0.5.0b (2013-Jul-23)
=======================================
1. Tolerate either -9 or 0 for unknown parent or affected status in PED files.
2. Refine the rules for inheritance and parental affected status for autosomal dominant inheritance models.
3. The ``autosomal_dominant``, ``autosomal_recessive``, and ``de_novo`` mutation tools have received the following improvements.

    -  improved speed (especially when there are multiple families)
    -  by default, all columns in the variant table are reported and no conditions are placed on the returned variants.  That is, as long as the variant meets
       the inheritance model, it will be reported.
    -  the addition of a ``--columns`` option allowing one to override the above default behavior and report a subset of columns.
    -  the addition of a ``--filter`` option allowing one to override the above default behavior and filter reported variants based on specific criteria.

4. The default minimum aligned sequencing depth for each variant reported by
the ``de_novo`` tool is 0.  Greater stringency can be applied with the ``-d``
option.

0.4.0b (2013-Jun-12)
=======================================
1. Added new ``gt_ref_depths``, ``gt_alt_depths``, and ``gt_quals`` columns.
2. Added a new ``--show-samples`` option to the ``query`` module to display samples with alternate allele genotypes.
3. Improvements and bug fixes for installation.

0.3.0b
=======================================
1. Improved speed for adding custom annotations.
2. Added GERP conserved elements.
3. Optionally addition of GERP conservation scores at base pair resolution.
4. Move annotation files to Amazon S3.

