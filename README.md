# 2ptPipeline
For development and testing of a 2-point statistics pipeline, using TreeCorr

# Usage: python w_pipeline.py <path/to/config/file> ...

optional arguments:

  -h, --help    show this help message and exit
  
  -bin_slop BIN_SLOP    specify treecorr bin_slop parameter (float, default=0.4)
                        
  -num_threads NUM_THREADS    specify number of processors available (default=16)
                       
  -save_cats SAVE_CATS    save out fits catalogues (per correlation) for inspection
  
  -verbosity VERBOSITY  specify treecorr verbosity (int[0,3], default=0)
  
  -down DOWN            specify factor = Nrandoms / Ngalaxies (float,
                        default=10. // set to 0. for no downsampling)
                        
  -p [P [P ...]]    override config-file parameters e.g. -p section.param=value (make sure no trailing slashes in paths)
                        
  -index [INDEX [INDEX ...]]    give indices of correlations in the config file that you desire to run -- others will be skipped. E.g. -index 0 will run only the first correlation
                        
See also the comments in the example_clustering_config.ini file

# Jackknife usage: python skyknife.py <path/to/config/file> ...

Run this on each randoms catalogue BEFORE running the correlation w_pipeline.py -- specify the other catalogues within the config file (exportto=). See notes in [jackknife] section of config file for more details.

optional arguments:
                          
  -p [P [P ...]]    with syntax "-p <arg1>=<value1>.." specify any of the
                  following args: catpath, ra_col, dec_col, z_col, r_col,
                  do_3d, sc_tol, sz_tol, min_scale_deg, plot


# Note: currently require separate config files for angular/projected stats
