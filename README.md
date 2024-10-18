# Genomic-analysis-tutorial
Last login: Tue Oct 15 14:05:03 2024 from 192.168.25.53
(base) [***\jmagudha@*** ~]$ conda activate seekdeep
(seekdeep) [***\jmagudha@*** ~]$ ls
miniforge3  software
(seekdeep) [***\jmagudha@*** ~]$ cd software/
(seekdeep) [***\jmagudha@*** ~] software]$ ls
elucidator  SeekDeep
(seekdeep) [***\jmagudha@*** ~] software]$ git clone https://github.com/kevin-wamae/seekdeep-workflows.git
Cloning into 'seekdeep-workflows'...
remote: Enumerating objects: 427, done.
remote: Counting objects: 100% (55/55), done.
remote: Compressing objects: 100% (41/41), done.
remote: Total 427 (delta 17), reused 46 (delta 13), pack-reused 372 (from 1)
Receiving objects: 100% (427/427), 192.22 MiB | 17.38 MiB/s, done.
Resolving deltas: 100% (166/166), done.
Updating files: 100% (73/73), done.
(seekdeep) [***\jmagudha@*** ~] software]$ cd seekdeep-workflows/
(seekdeep) [***\jmagudha@*** ~] seekdeep-workflows]$ ls
LICENSE    wf-demux-illumina-adaptors  wf-demux-nanopore-mids     wf-seekdeep-illumina-no-mids  wf-seekdeep-nanopore-no-mids
resources  wf-demux-illumina-mids      wf-seekdeep-illumina-mids  wf-seekdeep-nanopore-mids
(seekdeep) [***\jmagudha@*** ~] seekdeep-workflows]$ ls resources/
scripts
(seekdeep) [***\jmagudha@*** ~] seekdeep-workflows]$ cd resources/
(seekdeep) [***\jmagudha@*** ~] resources]$ ls
scripts
(seekdeep) [***\jmagudha@*** ~] resources]$ bash scripts/download_genomes.sh
--2024-10-18 14:26:47--  http://seekdeep.brown.edu/data/plasmodiumData/pf.tar.gz
Resolving seekdeep.brown.edu (seekdeep.brown.edu)... 128.148.254.107
Connecting to seekdeep.brown.edu (seekdeep.brown.edu)|128.148.254.107|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://seekdeep.brown.edu/data/plasmodiumData/pf.tar.gz [following]
--2024-10-18 14:26:49--  https://seekdeep.brown.edu/data/plasmodiumData/pf.tar.gz
Connecting to seekdeep.brown.edu (seekdeep.brown.edu)|128.148.254.107|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 990343186 (944M) [application/x-gzip]
Saving to: ‘pfalciparum.tar.gz’

pfalciparum.tar.gz                               1%[>                                                                                                    ]  11.27M   354KB/s    eta 24m 43s^C
(seekdeep) [***\jmagudha@*** ~] resources]$ ls
pfalciparum.tar.gz  scripts
(seekdeep) [***\jmagudha@*** ~] resources]$ rm pfalciparum.tar.gz
(seekdeep) [***\jmagudha@*** ~] resources]$ cp -r /home/KWTRP/kkariuki/seekdeep-workflows/resources/genomes .
(seekdeep) [***\jmagudha@*** ~] resources]$ cp -r /home/KWTRP/kkariuki/seekdeep-workflows/resources/info .
(seekdeep) [***\jmagudha@*** ~] resources]$ ls
genomes  info  scripts
(seekdeep) [***\jmagudha@*** ~] resources]$ cd /data/isabella_group/data/aufi_2023/
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ ls
2024_10_08_ilri_illumina_miseq_2x300  input  run_files  temp
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ mv input 2024_10_08_ilri_illumina_miseq_2x300/
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ ls
2024_10_08_ilri_illumina_miseq_2x300  run_files  temp
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ mv run_files/ 2024_10_08_ilri_illumina_miseq_2x300/
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ ls
2024_10_08_ilri_illumina_miseq_2x300  temp
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ mv temp/ 2024_10_08_ilri_illumina_miseq_2x300/
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ ls
2024_10_08_ilri_illumina_miseq_2x300
(seekdeep) [***\jmagudha@*** ~] aufi_2023]$ cd /home/KWTRP/jmagudha/software/seekdeep-workflows/wf-seekdeep-illumina-mids
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ bash scripts/
1_get_target_info.sh  2_analysis.sh
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ bash scripts/1_get_target_info.sh
njhseq::PrimersAndMids::PrimersAndMids(const boost::filesystem::path&): error, /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/run_files/primers.txt doesn't exist

(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ bash scripts/1_get_target_info.sh
boost::filesystem::status: Permission denied [system:13]: "/home/KWTRP/kkariuki/software/seekdeep-workflows/resources/genomes/"
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ bash scripts/1_get_target_info.sh
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ SeekDeep
Version 3.0.2-dev
Programs
Use SeekDeep [PROGRAM] --help to see more details about each program
Commands are not case sensitive
SeekDeep
1) extractor
2) extractorByKmerMatching
3) extractorPairedEnd
4) kluster
5) makeSampleDirectories
6) processClusters
7) qluster
SeekDeepServer
1) genProjectConfig
2) popClusteringViewer
SeekDeepUtils
01) benchmarkControlMixturesOnProcessedClustersDir
02) benchmarkMultiTarAmpControlMixtures
03) benchmarkTarAmpControlMixtures
04) combineBasicResultsFiles
05) deRepPopClusDir
06) dryRunQualityFiltering
07) gatherInfoOnTargetedAmpliconSeqFile
08) genTargetInfoFromGenomes
09) getPossibleSampleNamesFromRawInput
10) primersToFasta
11) rBind
12) replaceUnderscores
13) runMultipleCommands
14) SampleBarcodeFileToSeekDeepInput
15) setupTarAmpAnalysis
16) variantCallOnSeqAndProtein
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ SeekDeep qluster --h
SeekDeep qluster
Cluster input sequences by collapsing on set differences between the sequences
                                      Required Options
                                         Clustering
                                       --par    Parameters filename to supply differences to allow to cluster, required unless technology flag used; required; default=; (std::string)
                                   Reading Sequence Input
                                     --fasta    Input sequence filename, only need 1, fasta text file; required; default=; (boost::filesystem::path)
                                   --fastagz    Input sequence filename, only need 1, fasta gzipped file; required; default=; (boost::filesystem::path)
                                     --fastq    Input sequence filename, only need 1, fastq text file; required; default=; (boost::filesystem::path)
                                   --fastqgz    Input sequence filename, only need 1, fastq gzipped file; required; default=; (boost::filesystem::path)
                                      Optional Options
                                     Additional Output
                             --additionalOut    Additional out filename for sorting final results; default=; (std::string)
                             --createMinTree    Create Pseudo minimum Spanning Trees For Mismatches for Final Clusters; default=false; (bool)
                                 --snapShots    Output Snap Shots of clustering results after each iteration; default=false; (bool)
           --writeOutFinalAllByAllComparison    Write out all pairwise comparisons between all the final clusters; default=false; (bool)
                 --writeOutFinalInternalSnps    Write out Internal (within the clusters) SNP class, useful for debugging if over collapsing is happening; default=false; (bool)
                        --writeOutInitalSeqs    Write out the sequences that make up each cluster; default=false; (bool)
                                         Alignment
                           --caseInsensitive    Use Case Insensitive Scoring for alignment; default=false; (bool)
                              --countEndGaps    Count End Gaps; default=false; (bool)
                                     --degen    Use Degenerative Base Scoring for alignment; default=false; (bool)
                                       --gap    Gap Penalties for Middle Gap; default=5,1; (std::string)
                                    --gapAll    Gap Penalties for All (middle and end gaps); default=5,1; (std::string)
                                   --gapLeft    Gap Penalties for Left End Gap; default=5,1; (std::string)
                                  --gapRight    Gap Penalties for Right End Gap; default=0,0; (std::string)
                                     --lessN    Use Degenerative Base Scoring but use a lesser score for the degenerative bases; default=false; (bool)
                                     --local    Local alignment; default=false; (bool)
                                     --match    Match score for alignment; default=2; (int32_t)
                                  --mismatch    Mismatch score for alignment; default=-2; (int32_t)
                            --noAlignCompare    Do comparisons without globally aligning; default=false; (bool)
               --noHomopolymerIndelWeighting    Don't do Homopolymer Weighting; default=false; (bool)
                               --scoreMatrix    Score Matrix Filename; default=; (std::string)
                                     Caching Alignments
                                --alnInfoDir    Alignment Info Cache Directory Name; default=; (std::string)
                             --outAlnInfoDir    Alignment Info Cache Out Directory Name; default=; (std::string)
                                          Chimeras
               --chiKeepLowQaulityMismatches    When marking chimeras also consider low quality mismatches, these are removed by default to prevent errors from incorrectly mising chimeras but could also hurt chimera marking; default=false; (bool)
                             --chiPosSpacing    The amount of shared sequence inbetween difference to consider a sequence a chimera of two parent sequences; default=3; (uint32_t)
                            --noMarkChimeras    Don't do chimera marking; default=false; (bool)
                                  --parFreqs    Parent freq multiplier cutoff; default=2; (double)
                                         Clustering
                               --checkAmount    Number of top clusters to check; default=100; (uint32_t)
                                  --converge    Keep clustering at each iteration until there is no more collapsing, could increase run time significantly; default=false; (bool)
                               --diffCutOffs    Difference Cutoff to form Nuc Comp Clusters when --useNucComp is used; default=0.1; (std::string)
          --dontRecalLowFreqMismatchAndReRun    Don't Recal Low Freq Mismatch And Re-Run Clustering Step; default=false; (bool)
                            --fastClustering    Skip comparisons if their nucleotide composition differs; default=false; (bool)
                               --findBestNuc    Find Best Nucleotide Cluster when --useNucComp is used; default=true; (bool)
                               --kCompareLen    kmer Compare Length for when bining by kmers first for when --useKmerBinning is used; default=10; (uint32_t)
                                --kmerCutOff    kmer Cut Off for when --useKmerBinning is used; default=0.8; (double)
                          --leaveOutSinglets    Leave out singlet clusters out of all analysis; default=false; (bool)
                                 --nucCutOff    Fraction Difference in nucleotide composition cut off for when --fastClustering is used; default=0.05; (double)
                             --singletCutOff    Naturally the cut off for being a singlet is by default 1 but can use --singletCutOff to raise the number; default=1; (uint32_t)
                          --startWithSingles    Start The Clustering With Singletons, rather then adding them afterwards; default=false; (bool)
                            --useKmerBinning    Use Kmer Binning for initial clustering to speed up clustering; default=false; (bool)
                                --useNucComp    Cluster on Nucleotide Composition First; default=false; (bool)
                            Low Frequency Mismatch Determination
                             --expandKmerPos    Expand Kmer Position Found At; default=false; (bool)
                            --expandKmerSize    Expand Kmer Size for extending where kmers where found; default=5; (uint32_t)
                                 --kAnywhere    Count Kmers without regard for position; default=false; (bool)
                                   --kLength    Kmer Length; default=9; (uint32_t)
                                 --runCutOff    Kmer frequency cut off for a mismatch to be considered low frequency; default=.45%,10; (std::string)
                               Mismatch Quality Determination
                                 --qualThres    Quality Thresholds, should go PrimaryQual,SecondaryQual; default=20,15; (std::string)
                           --qualThresWindow    Quality Threshold Window Length; default=2; (uint32_t)
                                       OTU Clustering
                                   --onPerId    Cluster on Percent Identity Instead; default=false; (bool)
                                       --otu    Collapse on this OTU percentage, should be between (0,1); default=0.99; (double)
                                    --regOtu    Collapse on percent identity calculated using regular otu percent identity rather than using only high quality differences; default=false; (bool)
                                      Output Directory
                                      --dout    Output Directory Name; default=./; (std::string)
                              --overWriteDir    If the directory already exists over write it; default=false; (bool)
                                       Postprocessing
                               --development    output larger amount of data; default=false; (bool)
                                        Pre-process
                                  --trimBack    Trim back of the input sequence by this much; default=0; (uint32_t)
                                 --trimFront    Trim front of the input sequences by this much; default=0; (uint32_t)
                               --trimToLocal    When trimming to a set sequence use local alignment; default=false; (bool)
                        --trimToOnlyMatching    When trimming to a set sequence, trim to only matching seq; default=false; (bool)
                                 --trimToSeq    Trim input to this sequence; default=; (std::string)
                              --trimToWithin    When trimming to a set sequence, search within this many bases from the back; default=100; (uint32_t)
                                       Preprocessing
                   --keepDownloadSampledFile    Keep down sampled file; default=false; (bool)
                                   --qualRep    Per base quality score calculation for initial unique clusters collapse; default=median; (std::string)
                                  --qualTrim    Low Quality Cut Off; default=3; (uint32_t)
                             --smallReadSize    A cut off to remove small reads; default=18; (uint32_t)
                               --useAllInput    use all input reads even for large input; default=false; (bool)
                                 --useCutOff    the cut off for input size, will down sample the file if more than this, helps to control memory usage; default=50000; (uint32_t)
                                   Reading Sequence Input
                                     --lower    How to handle Lower Case Bases; default=remove; (std::string)
                                 --processed    Processed, Input Sequence Name has a suffix that contains abundance info; default=false; (bool)
                                --removeGaps    Remove Gaps from Input Sequences; default=false; (bool)
                          --trimAtWhiteSpace    Remove everything after first whitespace character in input sequence name; default=false; (bool)
                                         Technology
                                       --454    Flag to indicate reads are 454; default=false; (bool)
                                        --hq    When the --illumina,--454,or --ionTorrent flag is on also allow this many high quality mismatch to the defaults for those technology; default=0; (uint32_t)
                                  --illumina    Flag to indicate reads are Illumina; default=false; (bool)
                  --illuminaAllLowMismatches    Flag to collapse low quality and low frequency errors; default=false; (bool)
                  --illuminaAllowHomopolyers    Flag to indicate reads are Illumina but also handle homopolymer indels that may be from long polymers from SWGA TAQ; default=false; (bool)
                                --ionTorrent    Flag to indicate reads are IonTorrent and therefore turns on --adjustHomopolyerRuns and --qualTrim; default=false; (bool)
                                       Writing Output
                                --appendFile    Append to file; default=false; (bool)
                                       --out    Out Filename; default=output; (boost::filesystem::path)
                                 --overWrite    Over Write Existing Files; default=false; (bool)
                                       Miscellaneous
             --BackUpIlluminaSampleNumberPos    Back Up Illumina Sample Number Pos; default=12; (uint32_t)
             --BackUpIlluminaSampleRegPatStr    Back Up Illumina Sample Reg Pat Str; default=([A-Za-z0-9_]+):([0-9]+):([A-Za-z0-9-]+):([0-9]+):([0-9]+):([0-9]+):([0-9]+) ([12]):([NY]):([0-9]):([A-Za-z0-9_+:-]+) ([A-z0-9_|+-]+)( .*)?; (std::string)
                   --IlluminaSampleNumberPos    Illumina Sample Number Pos; default=11; (uint32_t)
                   --IlluminaSampleRegPatStr    Illumina Sample Reg Pat Str; default=([A-Za-z0-9_]+):([0-9]+):([A-Za-z0-9-]+):([0-9]+):([0-9]+):([0-9]+):([0-9]+) ([12]):([NY]):([0-9]):([AGCTN+]+); (std::string)
                      --adjustHomopolyerRuns    Adjust homopolymer runs to be same quality scores; default=false; (bool)
                                    --binPar    Parameters Filename for when reads are binned; default=; (std::string)
                          --breakoutClusters    Breakout Internal Clusters In case of over collapsed haplotypes; default=false; (bool)
                           --collapseTandems    Collapsing clusters if they only differ by gaps in tandem repeats; default=false; (bool)
           --collapseTandemsAllowableTandems    When collapse tandem repeat gaps, allow this many tandem repeat gap to allow collapse; default=1; (uint32_t)
             --collapseTandemsFreqMultiplier    When collapse tandem repeat gaps, larger cluster's frequency must be this many times the frequency of the smaller cluster; default=6; (double)
--collapseTandemsLowQualityMismatchesAllowed    When collapse tandem repeat gaps, allow this many low quality mismatches to also exist; default=1; (uint32_t)
                             --compPerCutOff    Percentage of reads in one direction Cut Off; default=0.98; (double)
                --countIlluminaSampleNumbers    Count Illumina Sample Numbers; default=false; (bool)
                                     --debug    Debug; default=false; (bool)
--dontFilterToMostCommonIlluminaSampleNumber    Don't Filter To Most Common Illumina Sample Number; default=false; (bool)
                                --initialPar    Parameters Filename for when doing non singlet analysis first, otherwise defaults to regular parameters; default=; (std::string)
                            --refFastq,--ref    Reference Fasta or Fastq File Name; default=; (boost::filesystem::path)
                                    --refGap    Gap Penalties for Ref Middle Gap; default=5,1; (std::string)
                                 --refGapAll    Gap Penalties for Ref All; default=5,1; (std::string)
                                --refGapLeft    Gap Penalties for Ref Left End Gap; default=0,0; (std::string)
                               --refGapRight    Gap Penalties for Ref Right End Gap; default=0,0; (std::string)
                                  --refLower    What to do about lower case bases in ref seqs; default=; (std::string)
                              --refProcessed    Reference Name Has Abundance Info; default=false; (bool)
                     --refTrimNameWhiteSpace    What to do about lower case bases in ref seqs; default=false; (bool)
                                --scoreBased    Scored Based Comparison For Alignments(defualt:event based); default=false; (bool)
                   --snpBreakoutMinGroupSize    A hard cut off for when breaking out clusters, clusters that larger(non-inclusive) than this are broken out; default=10; (uint32_t)
                             --snpFreqCutOff    Cut off for when breaking out snp frequencies; default=0.01; (double)
                                    --sortBy    Sort Clusters By; default=totalCount; (std::string)
                          --useCompPerCutOff    Throw out clusters that are made up reads of > 0% of reads in only one direction, used with Ion Torrent Reads; default=false; (bool)
                          --useMinLenNucComp    Use Nucleotide Composition of Only Front of seqs; default=true; (bool)
                                --verbose,-v    Verbose; default=false; (bool)
                                        Help Options
                                  --getFlags    Print flags
                                   -h,--help    Print a more detail help message if available
                                        Examples
SeekDeep qluster --fastq inputSeqs.fastq --par parFile.txt
SeekDeep qluster --fastq inputSeqs.fastq --illumina   #use default Illumina parameters for collapsing instead of supplying a parameters file
SeekDeep qluster --fastq inputSeqs.fastq --ionTorrent #use default IonTorrent parameters for collapsing instead of supplying a parameters file
SeekDeep qluster --fastq inputSeqs.fastq --454        #use default 454 parameters for collapsing instead of supplying a parameters file
SeekDeep qluster --fastq inputSeqs.fastq --otu .99    #use default parameters to OTU clustering at an OTU threshold of .99 instead of supplying a parameters file
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3018
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-22:54:01      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:01:32      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:37:15      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:31:03      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:04:48      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    4:58:50      1 keklf-cls01
              2366   longrun blastx.s KWTRP\bb  R 46-05:10:14      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:06:34      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:01:11      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    3:52:41      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat job.3018.err
void njhseq::TarAmpAnalysisSetup::Samples::addSample(const string&) error, already have E3-k13 for AUFI2024_ama1_k13-469_k13-675_Pool51
With input: 469-A, MID01

/var/spool/slurm/slurmd/job03018/slurm_script: line 93: ./runAnalysis.sh: No such file or directory
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3019
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-22:58:19      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:05:50      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:41:33      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:35:21      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:09:06      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:03:08      1 keklf-cls01
              2366   longrun blastx.s KWTRP\bb  R 46-05:14:32      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:10:52      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:05:29      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    3:56:59      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  job.3019.err  job.3019.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat job.3019.err
static int njhseq::SeekDeepUtilsRunner::setupTarAmpAnalysis(const njh::progutils::CmdArgs&): There is 1 error.
bool njhseq::TarAmpAnalysisSetup::TarAmpPars::checkForOutDir(njhseq::VecStr&) const: error, out directory "/data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep" already exists, must remove by hand will not overwrite


/var/spool/slurm/slurmd/job03019/slurm_script: line 93: ./runAnalysis.sh: No such file or directory
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ rm -r /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3020
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-23:00:16      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:07:47      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:43:30      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:37:18      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:11:03      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:05:05      1 keklf-cls01
              2366   longrun blastx.s KWTRP\bb  R 46-05:16:29      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:12:49      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:07:26      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    3:58:56      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  job.3019.err  job.3019.out  job.3020.err  job.3020.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat job.3020.err
njhseq::TarAmpAnalysisSetup::TarAmpAnalysisSetup(njhseq::TarAmpAnalysisSetup::TarAmpPars), error mismatch in the MIDs supplied in ID file and the MID names in sample names file
the following MIDs were found in the ID file but not in the sample names file: MID25, MID24, MID22, MID19, MID26, MID17, MID20, MID14, MID15, MID11, MID21, MID23, MID18, MID16, MID12, MID09, MID10

/var/spool/slurm/slurmd/job03020/slurm_script: line 93: ./runAnalysis.sh: No such file or directory
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ rm -r /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3021
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-23:02:25      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:09:56      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:45:39      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:39:27      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:13:12      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:07:14      1 keklf-cls01
              3021   highmem seekdeep KWTRP\jm  R       0:06      1 keklf-cls02
              2366   longrun blastx.s KWTRP\bb  R 46-05:18:38      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:14:58      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:09:35      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    4:01:05      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-23:02:48      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:10:19      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:46:02      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:39:50      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:13:35      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:07:37      1 keklf-cls01
              3021   highmem seekdeep KWTRP\jm  R       0:29      1 keklf-cls02
              2366   longrun blastx.s KWTRP\bb  R 46-05:19:01      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:15:21      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:09:58      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    4:01:28      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ s
bash: s: command not found...
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  job.3019.err  job.3019.out  job.3020.err  job.3020.out  job.3021.err  job.3021.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat job.3021.err
ERRORS FOUND!!
Read Warnings in /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep/WARNINGS_PLEASE_READ.txt
Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

/bin/ls: cannot access 'popClustering/*/analysis/selectedClustersInfo.tab.txt.gz': No such file or directory
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep/WARNINGS_PLEASE_READ.txt
The following files were found but didn't match any input sample names in "/data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/run_files/sampleNames.txt"
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool1
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool1_S1_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool1_S1_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool10
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool10_S10_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool10_S10_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool11
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool11_S11_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool11_S11_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool12
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool12_S12_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool12_S12_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool13
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool13_S13_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool13_S13_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool14
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool14_S14_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool14_S14_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool15
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool15_S15_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool15_S15_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool16
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool16_S16_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool16_S16_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool17
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool17_S17_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool17_S17_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool18
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool18_S18_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool18_S18_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool19
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool19_S19_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool19_S19_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool2
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool2_S2_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool2_S2_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool20
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool20_S20_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool20_S20_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool21
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool21_S21_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool21_S21_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool22
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool22_S22_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool22_S22_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool23
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool23_S23_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool23_S23_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool24
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool24_S24_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool24_S24_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool25
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool25_S25_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool25_S25_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool26
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool26_S26_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool26_S26_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool27
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool27_S27_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool27_S27_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool28
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool28_S28_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool28_S28_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool29
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool29_S29_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool29_S29_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool3
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool3_S3_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool3_S3_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool30
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool30_S30_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool30_S30_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool31
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool31_S31_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool31_S31_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool32
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool32_S32_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool32_S32_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool33
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool33_S33_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool33_S33_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool34
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool34_S34_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool34_S34_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool35
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool35_S35_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool35_S35_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool36
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool36_S36_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool36_S36_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool37
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool37_S37_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool37_S37_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool38
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool38_S38_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool38_S38_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool39
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool39_S39_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool39_S39_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool4
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool4_S4_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool4_S4_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool40
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool40_S40_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool40_S40_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool41
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool41_S41_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool41_S41_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool42
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool42_S42_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool42_S42_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool43
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool43_S43_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool43_S43_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool44
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool44_S44_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool44_S44_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool45
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool45_S45_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool45_S45_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool46
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool46_S46_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool46_S46_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool47
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool47_S47_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool47_S47_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool48
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool48_S48_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool48_S48_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool49
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool49_S49_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool49_S49_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool5
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool5_S5_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool5_S5_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool50
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool50_S50_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool50_S50_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool6
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool6_S6_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool6_S6_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool7
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool7_S7_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool7_S7_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool8
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool8_S8_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool8_S8_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool9
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool9_S9_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool9_S9_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-k13-469-k13-675-mdr1-Pool51
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-k13-469-k13-675-mdr1-Pool51_S51_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-k13-469-k13-675-mdr1-Pool51_S51_L001_R2_001.fastq.gz
        Possible Sample Name: Undetermined
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/Undetermined_S0_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/Undetermined_S0_L001_R2_001.fastq.gz
The following files were expected but were not found
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool50
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool48
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool47
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool45
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool44
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool43
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool42
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool37
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool36
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool35
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool34
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool32
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool31
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool15
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool30
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool16
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool40
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool9
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool49
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool18
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool10
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool39
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool6
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool8
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool4
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool51
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool12
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool7
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool1
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool3
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool19
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool33
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool25
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool2
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool11
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool38
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool5
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool14
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool46
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool24
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool26
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool17
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool20
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool21
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool13
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool27
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool28
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool22
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool23
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool41
        Sample: AUFI2024_ama1_k13-469_k13-675_Pool29

(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ rm -r /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3023
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-23:08:38      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:16:09      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:51:52      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:45:40      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:19:25      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:13:27      1 keklf-cls01
              3022   highmem amrfind. KWTRP\am  R       4:29      1 keklf-cls02
              3023   highmem seekdeep KWTRP\jm  R       0:06      1 keklf-cls04
              2366   longrun blastx.s KWTRP\bb  R 46-05:24:51      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:21:11      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:15:48      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    4:07:18      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  job.3019.err  job.3019.out  job.3020.err  job.3020.out  job.3021.err  job.3021.out  job.3023.err  job.3023.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat job.3023.err
ERRORS FOUND!!
Read Warnings in /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep/WARNINGS_PLEASE_READ.txt
Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

Error, "" needs to exist

/bin/ls: cannot access 'popClustering/*/analysis/selectedClustersInfo.tab.txt.gz': No such file or directory
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ cat  /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep/WARNINGS_PLEASE_READ.txt
The following files were found but didn't match any input sample names in "/data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/run_files/sampleNames.txt"
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool1
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool1_S1_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool1_S1_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool10
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool10_S10_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool10_S10_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool11
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool11_S11_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool11_S11_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool12
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool12_S12_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool12_S12_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool13
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool13_S13_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool13_S13_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool14
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool14_S14_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool14_S14_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool15
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool15_S15_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool15_S15_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool16
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool16_S16_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool16_S16_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool17
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool17_S17_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool17_S17_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool18
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool18_S18_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool18_S18_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool19
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool19_S19_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool19_S19_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool2
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool2_S2_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool2_S2_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool20
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool20_S20_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool20_S20_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool21
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool21_S21_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool21_S21_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool22
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool22_S22_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool22_S22_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool23
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool23_S23_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool23_S23_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool24
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool24_S24_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool24_S24_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool25
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool25_S25_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool25_S25_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool26
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool26_S26_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool26_S26_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool27
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool27_S27_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool27_S27_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool28
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool28_S28_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool28_S28_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool29
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool29_S29_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool29_S29_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool3
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool3_S3_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool3_S3_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool30
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool30_S30_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool30_S30_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool31
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool31_S31_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool31_S31_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool32
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool32_S32_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool32_S32_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool33
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool33_S33_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool33_S33_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool34
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool34_S34_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool34_S34_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool35
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool35_S35_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool35_S35_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool36
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool36_S36_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool36_S36_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool37
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool37_S37_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool37_S37_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool38
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool38_S38_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool38_S38_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool39
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool39_S39_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool39_S39_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool4
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool4_S4_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool4_S4_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool40
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool40_S40_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool40_S40_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool41
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool41_S41_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool41_S41_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool42
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool42_S42_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool42_S42_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool43
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool43_S43_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool43_S43_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool44
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool44_S44_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool44_S44_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool45
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool45_S45_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool45_S45_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool46
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool46_S46_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool46_S46_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool47
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool47_S47_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool47_S47_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool48
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool48_S48_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool48_S48_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool49
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool49_S49_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool49_S49_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool5
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool5_S5_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool5_S5_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool50
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool50_S50_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool50_S50_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool6
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool6_S6_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool6_S6_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool7
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool7_S7_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool7_S7_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool8
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool8_S8_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool8_S8_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-ama1-k13-469-k13-675-Pool9
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool9_S9_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-ama1-k13-469-k13-675-Pool9_S9_L001_R2_001.fastq.gz
        Possible Sample Name: AUFI2024-k13-469-k13-675-mdr1-Pool51
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-k13-469-k13-675-mdr1-Pool51_S51_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/AUFI2024-k13-469-k13-675-mdr1-Pool51_S51_L001_R2_001.fastq.gz
        Possible Sample Name: Undetermined
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/Undetermined_S0_L001_R1_001.fastq.gz
                /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/input/fastq/Undetermined_S0_L001_R2_001.fastq.gz
The following files were expected but were not found
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool48
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool47
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool43
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool41
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool39
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool37
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool49
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool36
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool35
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool33
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool31
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool13
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool11
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool14
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool46
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool15
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool8
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool5
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool26
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool10
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool51
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool45
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool40
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool9
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool29
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool38
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool6
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool4
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool44
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool1
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool24
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool2
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool16
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool50
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool34
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool17
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool18
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool19
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool21
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool25
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool20
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool22
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool7
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool27
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool30
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool3
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool23
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool42
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool32
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool12
        Sample: AUFI2024_ama1_k13-469-k13-675-Pool28

(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  job.3018.err  job.3018.out  job.3019.err  job.3019.out  job.3020.err  job.3020.out  job.3021.err  job.3021.out  job.3023.err  job.3023.out  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ rm job.*
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ ls
input  scripts
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ rm -r /data/isabella_group/data/aufi_2023/2024_10_08_ilri_illumina_miseq_2x300/output/analysis/2024_10_18-01-seekdeep
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ sbatch scripts/2_analysis.sh
Submitted batch job 3024
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$ squeue
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2895       gpu BEAST_sk KWTRP\so  R 6-23:14:38      3 keklf-cls[04,06-07]
              2994       gpu scale_10 KWTRP\so  R 1-04:22:09      3 keklf-cls[04,06-07]
              3001       gpu shape_1_ KWTRP\so  R   22:57:52      3 keklf-cls[04,06-07]
              3002       gpu weight_5 KWTRP\so  R   22:51:40      3 keklf-cls[04,06-07]
              3009   highmem iqtree_r KWTRP\pj  R    5:25:25      1 keklf-cls01
              3011   highmem modeltes KWTRP\pj  R    5:19:27      1 keklf-cls01
              3022   highmem amrfind. KWTRP\am  R      10:29      1 keklf-cls02
              3024   highmem seekdeep KWTRP\jm  R       1:19      1 keklf-cls04
              2366   longrun blastx.s KWTRP\bb  R 46-05:30:51      3 keklf-cls[01-02,06]
              3008   longrun    sadie KWTRP\bk  R    5:27:11      2 keklf-cls[01-02]
              3010   longrun    sadie KWTRP\bk  R    5:21:48      1 keklf-cls02
              3017   longrun   presto KWTRP\bk  R    4:13:18      2 keklf-cls[01-02]
(seekdeep) [***\jmagudha@*** ~] wf-seekdeep-illumina-mids]$
