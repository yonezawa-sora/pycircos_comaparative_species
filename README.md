# PYCIRCOS COMPARATIVE SPECIES 

- Gene Ontology (GO_Slim)の共通性をcircos plotで可視化できないかと考えて作成しました

&nbsp;

## Data

1. human

    1. chromosome size (Assembly version)

    - hg38(GRCh38)
    - <>
    - <https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/001/405/GCA_000001405.29_GRCh38.p14/GCA_000001405.29_GRCh38.p14_assembly_report.txt>
    - 上記のリンクを元にchromosomeのサイズファイルを作成
    
    &nbsp;

    2. HN-score

    - <https://figshare.com/articles/dataset/Table_S5_HN-score_data_for_all_human_genes/23944935>
    - figshareにアップロードされているHN-scoreのデータをダウンロード
    - Convert to Ensembl gene ID
    - [g:profiler](https://biit.cs.ut.ee/gprofiler/convert)にアクセス
    - Ensembl genes 110のバージョンを使用
    - __重複してヒットした場合は遺伝子シンボルが同じIDを選択__
    - すでに｢Previous name｣になっている場合はHGNCにアクセスし､再度手作業でIDを取得
    ![Alt text](./data/g:profiler.png)

    ### 2023/11/05

    - 遺伝子の抽出の条件を変更したので再度同じ作業を実行
    - 重複してヒットした場合は遺伝子シンボルが同じIDを選択
    - HGNC accessed 2023/11/05
    - g:profiler accessed 2023/11/05

    #### Gene Convert (previous gene name -> current gene name)

    1. CDRT1: FBXW10B <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:14379>
    2. C7ORF61: SPACDR <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:22135>
    3. DDX58: RIGI <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:19102>
    4. C16ORF71: DNAAF8 <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:25081>
    5. GPR1: CMKLR2 <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:4463>



    

&nbsp;

2. mouse

&nbsp;

3. __rice__

    1. chromosome size (Assembly version)

    - IRGSP-1.0
    - <https://plants.ensembl.org/Oryza_sativa/Info/Annotation/#assembly>
    - <https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/001/433/935/GCA_001433935.1_IRGSP-1.0/GCA_001433935.1_IRGSP-1.0_assembly_report.txt>
    - 上記のリンクを元にchromosomeのサイズファイルを作成

    &nbsp;

    2. HN-score

    - スコアをもとに抽出した遺伝子群のアノテーションをEnsembl Plants release 56にアクセスし取得