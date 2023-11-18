# PYCIRCOS COMPARATIVE SPECIES 

- Gene Ontology (GO_Slim)の共通性をcircos plotで可視化できないかと考えて作成しました

&nbsp;

## Prepared Data

1. chromosome size

- 本当は[NCBI datasets command](https://www.ncbi.nlm.nih.gov/datasets/docs/v2/how-tos/genomes/get-genome-metadata/)を使ってうまく取得したいと考えたが､今回は手動で検索

    1. human (taxid: 9606)
        - hg38(GRCh38.p14)
        - <https://ftp.ncbi.nlm.nih.gov/genomes/all/annotation_releases/9606/GCF_000001405.40-RS_2023_10/GCF_000001405.40_GRCh38.p14_assembly_report.txt>
        - 上記のリンクを元にchromosomeのサイズファイルを作成

    2. mouse (taxid: )
        - GRCm39
        - <>

    3. rice (taxid: 39947)
        - IRGSP-1.0
        - <https://ftp.ncbi.nlm.nih.gov/genomes/all/annotation_releases/39947/102/GCF_001433935.1_IRGSP-1.0/GCF_001433935.1_IRGSP-1.0_assembly_report.txt>
        - 上記のリンクを元にchromosomeのサイズファイルを作成

&nbsp;

2. HN-score (human and mouse)

    1. human 
        - <https://figshare.com/articles/dataset/Table_S5_HN-score_data_for_all_human_genes/23944935>
        - figshareにアップロードされているHN-scoreのデータをダウンロード
        - 使用されているgene nameに変更があることが判明したのでEnsembl gene IDに変換
        - [g:profiler](https://biit.cs.ut.ee/gprofiler/convert)にアクセス
        - Ensembl genes 110のバージョンを使用
        - __重複してヒットした場合は遺伝子シンボルが同じIDを選択__
        - すでに｢Previous name｣になっている場合はHGNCにアクセスし､再度手作業でIDを取得

        ### 2023/11/05

        - 遺伝子の抽出の条件を変更したので再度同じ作業を実行
        - 重複してヒットした場合は遺伝子シンボルが同じIDを選択
        - HGNC accessed 2023/11/05
        - g:profiler accessed 2023/11/05

        ### 2023/11/13

        - ファイルを間違って消してしまい､更にgitで追跡していなかったので再度同じ作業(g:convert)を実行
        - 重複してヒットした場合は遺伝子シンボルが同じIDを選択
        - HGNC accessed 2023/11/13
        - g:profiler accessed 2023/11/13

        #### Gene Convert (previous gene name -> current gene name) (2023/11/13)

            1. CDRT1: FBXW10B <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:14379>
            2. C7ORF61: SPACDR <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:22135>
            3. DDX58: RIGI <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:19102>
            4. C16ORF71: DNAAF8 <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:25081>
            5. GPR1: CMKLR2 <https://www.genenames.org/data/gene-symbol-report/#!/hgnc_id/HGNC:4463>

&nbsp;

