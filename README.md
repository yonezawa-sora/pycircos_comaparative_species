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
        - <https://ftp.ncbi.nlm.nih.gov/genomes/all/annotation_releases/10090/GCF_000001635.27-RS_2023_04/GCF_000001635.27_GRCm39_assembly_report.txt>
        - 上記のリンクを元にchromosomeのサイズファイルを作成

    3. rice (taxid: 39947)
        - IRGSP-1.0
        - <https://ftp.ncbi.nlm.nih.gov/genomes/all/annotation_releases/39947/102/GCF_001433935.1_IRGSP-1.0/GCF_001433935.1_IRGSP-1.0_assembly_report.txt>
        - 上記のリンクを元にchromosomeのサイズファイルを作成

&nbsp;

2. HN-score (human and mouse)

    1. human 
        - <https://doi.org/10.6084/m9.figshare.23944935.v2>
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
    
    2. mouse
        - <https://doi.org/10.6084/m9.figshare.23945073.v2>
        - figshareにアップロードされているHN-scoreのデータをダウンロード
        - 使用されているgene nameに変更があることが判明したのでEnsembl gene IDに変換
        - [g:profiler](https://biit.cs.ut.ee/gprofiler/convert)にアクセス
        - Ensembl genes 110のバージョンを使用 (AFFY_MOGENE_2_1_ST_V1)
        - __重複してヒットした場合は遺伝子シンボルが同じIDを選択__
        - ない場合はMGIでも変換して検索
        - figshareのデータを更新

        #### Gene Convert (previous gene name -> current gene name) (2023/11/24 accessed) (MGI accessed 2023/11/24)

            1. GM21738: [対応するEnsembl gene IDなし]
            2. GM38100: Becn2 <https://www.informatics.jax.org/marker/MGI:2684950> 
            3. FAM71D: Garin2 <https://www.informatics.jax.org/marker/MGI:1918147>
            4. GM5741: Gng14 <https://www.informatics.jax.org/marker/MGI:3645690>
            5. AF366264: Semp2l2a <https://www.informatics.jax.org/marker/MGI:2667157>
            6. GM10720: ENSMUSG00000074564 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000074564>
            7. GM10800: ENSMUSG00000075014 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000075014>
            8. GM10801: ENSMUSG00000075015 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000075015>
            9. 1700007K13RIK: Pierce1 <https://www.informatics.jax.org/marker/MGI:1916577>
            10. Snapc1l: ENSMUSG00000114046 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000114046>
            11. GM10718: ENSMUSG00000095186 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000095186>
            12. GM11032: ENSMUSG00000079010 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000079010>
            13. GM43518: ENSMUSG00000105875 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000105875>
            14. A730071L15RIK: ENSMUSG00000096923 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000096923>
            15. 4930558C23RIK: Ctxnd2 <https://www.informatics.jax.org/marker/MGI:1914904>
            16. GM10799: ENSMUSG00000075006 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000075006>
            17. 4632433K11RIK: ENSMUSG00000116184 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000116184>
            18. GM10203: ENSMUSG00000067292 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000067292>
            19. G530012D18RIK: ENSMUSG00000094127 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000094127>
            20. GM50364: ENSMUSG00000117732 (MGIでは変換が出てきた) <https://useast.ensembl.org/Mus_musculus/Gene/Idhistory?g=ENSMUSG00000117732>







&nbsp;

3. Gene Ontology (GOSlim)

- <https://feb2023-plants.ensembl.org/index.html> Ensembl Plants 56
