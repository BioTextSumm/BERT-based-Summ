# BERT-based-Summ
BERT-based Biomedical Text Summarizer

1. Download version 1 or version 2 of the BERT-based biomedical text summarizer.
     - Version 1 uses Euclidean distance in the clustering step.
     - Version 2 uses Cosine similarity in the clustering step.
2. Extract the zip file.
3. Download the BERT repository from https://github.com/google-research/bert, and copy the files to the BERT directory already available with the summarizer.
4. Download a BERT pretrained model from https://github.com/google-research/bert or a BioBERT pretrained model from https://github.com/naver/biobert-pretrained, and copy the files to the BERT directory already available with the summarizer.
5. Copy your input document (preferably a txt file) to the INPUT directory already available with the summarizer.
6. Run the following script:
     - python Summarizer.py -i INPUT_FILE_NAME -o OUTPUT_FILE_NAME -c COMPRESSION_RATE -k NUMBER_OF_CLUSTERS
7. Four parameters must be specified when running the script:
     - INPUT_FILE_NAME is the name of input file already copied to the INPUT directory.
     - OUTPUT_FILE_NAME is the name of output file containing the summary that will be created in the OUTPUT directory.
     - COMPRESSION_RATE specifies the size of summary and takes a value in the range (0, 1).
     - NUMBER_OF_CLUSTERS specifies the number of final clusters in the clustering step.
   
8. After finishing the summarization process, the summary can be found in the OUTPUT directory already available with the summarizer. 

<hr>
<b>Final evaluation results</b>
<br>
<table>
     <tr>
          <td></td>
          <td>ROUGE-1</td>
          <td>ROUGE-2</td>
     </tr>
     <tr>
          <td>BERT-based summarizer (BERT-large)</td>
          <td>0.7504</td>
          <td>0.3312</td>
     </tr>
     <tr>
          <td>BERT-based summarizer (BioBERT-pubmed+pmc)</td>
          <td>0.7411</td>
          <td>0.3228</td>
     </tr>
     <tr>
          <td>BERT-based summarizer (BioBERT-pubmed)</td>
          <td>0.7376</td>
          <td>0.3203</td>
     </tr>
     <tr>
          <td>CIBS biomedical summarizer</td>
          <td>0.7345</td>
          <td>0.3187</td>
     </tr>
     <tr>
          <td>BERT-based summarizer (BioBERT-pmc)</td>
          <td>0.7309</td>
          <td>0.3164</td>
     </tr>
     <tr>
          <td>Bayesian biomedical summarizer</td>
          <td>0.7288</td>
          <td>0.3143</td>
     </tr>
     <tr>
          <td>BERT-based summarizer (BERT-base)</td>
          <td>0.7257</td>
          <td>0.3110</td>
     </tr>
     <tr>
          <td>SUMMA</td>
          <td>0.7098</td>
          <td>0.3022</td>
     </tr>
     <tr>
          <td>TexLexAn</td>
          <td>0.6982</td>
          <td>0.2979</td>
     </tr>
     <tr>
          <td>Lead baseline</td>
          <td>0.6116</td>
          <td>0.2311</td>
     </tr>
     <tr>
          <td>Random baseline</td>
          <td>0.5667</td>
          <td>0.1999</td>
     </tr>
</table>
