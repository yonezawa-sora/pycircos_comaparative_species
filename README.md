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

    

&nbsp;

2. mouse

&nbsp;

3. __rice__
    - IRGSP-1.0
    - <https://plants.ensembl.org/Oryza_sativa/Info/Annotation/#assembly>
    - <https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/001/433/935/GCA_001433935.1_IRGSP-1.0/GCA_001433935.1_IRGSP-1.0_assembly_report.txt>
    - 上記のリンクを元にchromosomeのサイズファイルを作成