# utl_why_proc_import_complicates_programming
Why proc import complicates programming.  Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.

    Why proc import complicates programming

    SAME result in WPS and SAS

    Orginal topic: Specifying variable names row using libname xlsx

    github (copy/paste from .sas file)
    https://github.com/rogerjdeangelis/utl_why_proc_import_complicates_programming

    Don't bother with 'proc import' it is not needed!!

    see
    https://communities.sas.com/t5/Base-SAS-Programming/specifying-variable-names-row-using-libname-xlsx/m-p/466604


    INPUT
    =====

      d:/xls/class.xlsx


          +-----------------------------------------------------------------
          |     A      |    B       |     C      |    D       |    E       |
          +-----------------------------------------------------------------
       1  | NAME       |   SEX      |    AGE     |  HEIGHT    |  WEIGHT    |
          +------------+------------+------------+------------+------------+
       2  | ALFRED     |    M       |    15      |    69      |    99      |
          +------------+------------+------------+------------+------------+
       3  | ALICE      |    F       |    13      |    58      |   110      |
          +------------+------------+------------+------------+------------+

    [SHEET1]


    PROCESS
    -------

      libname xel "d:/xls/class.xlsx";

      proc report data=xel.'sheet1$a2:e20'n;
      title "Why bother with 'proc import' SAS please deprecate it";
      run;quit;

      libname xel clear;


    OUTPUT
    ======

      Why bother with 'proc import' SAS please deprecate it

        Alfred   M         14         69      112#5
        Alice    F         13       56.5         84
        Barbara  F         13       65.3         98
        Carol    F         14       62.8      102.5
        Henry    M         14       63.5      102.5
        James    M         12       57.3         83
        Jane     F         12       59.8       84.5
        Janet    F         15       62.5      112.5
        Jeffrey  M         13       62.5         84
        John     M         12         59       99.5
        Joyce    F         11       51.3       50.5
        Judy     F         14       64.3         90
        Louise   F         12       56.3         77
        Mary     F         15       66.5        112
        Philip   M         16         72        150
        Robert   M         12       64.8        128
        Ronald   M         15         67        133
        Thomas   M         11       57.5         85
        William  M         15       66.5        112

    *                _                _       _
     _ __ ___   __ _| | _____      __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \    / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/   | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|    \__,_|\__,_|\__\__,_|

    ;

    libname xel "d:/xls/class.xlsx";
    data xel.sheet1;
     set sashelp.class;
    run;quit;
    libname xel clear;

    * see process foro SAS;

    *WPS;

    %utl_submit_wps64('
      libname xel excel "d:/xls/class.xlsx";
      proc report data=xel."sheet1$a2:e20"n;
      title "Why bother with proc import SAS please deprecate it";
      run;quit;
      libname xel clear;
    run;quit;
    ');

