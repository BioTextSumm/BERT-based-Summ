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
<b>Example</b>
<br>
The following script uses the file Input.txt as the input, runs the summarizer with a compression rate of 30 percent and a final cluster number of 4, and finally stores the summary in the file Output.txt:

     - python Summarizer.py -i Input.tx -o Output.txt -c 0.3 -k 4
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
          <td><b>0.7504</b></td>
          <td><b>0.3312</b></td>
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

<hr>
<b>Parameterization results (Euclidean distance)</b>
<br>
<table>
     <tr>
          <td></td>
          <td colspan=2>BERT-base</td>
          <td colspan=2>BERT-large</td>
          <td colspan=2>BioBERT-pmc</td>
          <td colspan=2>BioBERT-pubmed</td>
          <td colspan=2>BioBERT-pubmed+pmc</td>
     </tr>
     <tr>
          <td>K</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
     </tr>
     <tr>
          <td>2</td>
          <td>0.7221</td>
          <td>0.3087</td>
          <td>0.7434</td>
          <td>0.3264</td>
          <td>0.7243</td>
          <td>0.3094</td>
          <td>0.7269</td>
          <td>0.3122</td>
          <td>0.7369</td>
          <td>0.3195</td>
     </tr>
     <tr>
          <td>3</td>
          <td><b>0.7291</b></td>
          <td><b>0.3133</b></td>
          <td>0.7457</td>
          <td>0.3285</td>
          <td><b>0.7308</b></td>
          <td>0.3172</td>
          <td><b>0.7361</b></td>
          <td>0.3186</td>
          <td><b>0.7429</b></td>
          <td><b>0.3265</b></td>
     </tr>
     <tr>
          <td>4</td>
          <td>0.7224</td>
          <td>0.3107</td>
          <td><b>0.7507</b></td>
          <td><b>0.3329</b></td>
          <td>0.7299</td>
          <td><b>0.3189</b></td>
          <td>0.7354</td>
          <td><b>0.3187</b></td>
          <td>0.7399</td>
          <td>0.3234</td>
     </tr>
     <tr>
          <td>5</td>
          <td>0.7205</td>
          <td>0.3114</td>
          <td>0.7467</td>
          <td>0.3302</td>
          <td>0.7272</td>
          <td>0.3138</td>
          <td>0.7293</td>
          <td>0.3183</td>
          <td>0.7398</td>
          <td>0.3229</td>
     </tr>
     <tr>
          <td>6</td>
          <td>0.7199</td>
          <td>0.3099</td>
          <td>0.7415</td>
          <td>0.3249</td>
          <td>0.7239</td>
          <td>0.3134</td>
          <td>0.7276</td>
          <td>0.3146</td>
          <td>0.7352</td>
          <td>0.3199</td>
     </tr>
     <tr>
          <td>7</td>
          <td>0.7157</td>
          <td>0.3075</td>
          <td>0.7366</td>
          <td>0.3208</td>
          <td>0.7187</td>
          <td>0.3097</td>
          <td>0.7226</td>
          <td>0.3111</td>
          <td>0.7313</td>
          <td>0.3170</td>
     </tr>
     <tr>
          <td>8</td>
          <td>0.7179</td>
          <td>0.3079</td>
          <td>0.7334</td>
          <td>0.3183</td>
          <td>0.7194</td>
          <td>0.3089</td>
          <td>0.7198</td>
          <td>0.3074</td>
          <td>0.7272</td>
          <td>0.3122</td>
     </tr>
     <tr>
          <td>9</td>
          <td>0.7146</td>
          <td>0.3084</td>
          <td>0.7291</td>
          <td>0.3173</td>
          <td>0.7183</td>
          <td>0.3099</td>
          <td>0.7174</td>
          <td>0.3062</td>
          <td>0.7273</td>
          <td>0.3087</td>
     </tr>
     <tr>
          <td>10</td>
          <td>0.7127</td>
          <td>0.3054</td>
          <td>0.7284</td>
          <td>0.3137</td>
          <td>0.7186</td>
          <td>0.3102</td>
          <td>0.7162</td>
          <td>0.3036</td>
          <td>0.7196</td>
          <td>0.3080</td>
     </tr>
     <tr>
          <td>11</td>
          <td>0.7063</td>
          <td>0.2990</td>
          <td>0.7257</td>
          <td>0.3089</td>
          <td>0.7148</td>
          <td>0.3161</td>
          <td>0.7113</td>
          <td>0.2992</td>
          <td>0.7164</td>
          <td>0.3027</td>
     </tr>
     <tr>
          <td>12</td>
          <td>0.7034</td>
          <td>0.2968</td>
          <td>0.7203</td>
          <td>0.3101</td>
          <td>0.7094</td>
          <td>0.3088</td>
          <td>0.7087</td>
          <td>0.2995</td>
          <td>0.7117</td>
          <td>0.3006</td>
     </tr>
</table>

<hr>
<b>Parameterization results (Cosine similarity)</b>
<br>
<table>
     <tr>
          <td></td>
          <td colspan=2>BERT-base</td>
          <td colspan=2>BERT-large</td>
          <td colspan=2>BioBERT-pmc</td>
          <td colspan=2>BioBERT-pubmed</td>
          <td colspan=2>BioBERT-pubmed+pmc</td>
     </tr>
     <tr>
          <td>K</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
          <td>R-1</td>
          <td>R-2</td>
     </tr>
     <tr>
          <td>2</td>
          <td>0.7196</td>
          <td>0.3092</td>
          <td>0.7328</td>
          <td>0.3224</td>
          <td>0.7242</td>
          <td>0.3117</td>
          <td>0.7177</td>
          <td>0.3095</td>
          <td>0.7285</td>
          <td>0.3163</td>
     </tr>
     <tr>
          <td>3</td>
          <td>0.7169</td>
          <td>0.3102</td>
          <td><b>0.7377</b></td>
          <td><b>0.3275</b></td>
          <td>0.7249</td>
          <td><b>0.3131</b></td>
          <td>0.7224</td>
          <td>0.3089</td>
          <td><b>0.7328</b></td>
          <td><b>0.3204</b></td>
     </tr>
     <tr>
          <td>4</td>
          <td><b>0.7212</b></td>
          <td><b>0.3107</b></td>
          <td>0.7362</td>
          <td>0.3249</td>
          <td><b>0.7272</b></td>
          <td>0.3107</td>
          <td>0.7268</td>
          <td><b>0.3184</b></td>
          <td>0.7278</td>
          <td>0.3202</td>
     </tr>
     <tr>
          <td>5</td>
          <td>0.7152</td>
          <td>0.3068</td>
          <td>0.7361</td>
          <td>0.3259</td>
          <td>0.7212</td>
          <td>0.3082</td>
          <td><b>0.7298</b></td>
          <td>0.3165</td>
          <td>0.7295</td>
          <td>0.3199</td>
     </tr>
     <tr>
          <td>6</td>
          <td>0.7136</td>
          <td>0.3026</td>
          <td>0.7299</td>
          <td>0.3205</td>
          <td>0.7171</td>
          <td>0.3071</td>
          <td>0.7261</td>
          <td>0.3157</td>
          <td>0.7272</td>
          <td>0.3160</td>
     </tr>
     <tr>
          <td>7</td>
          <td>0.7107</td>
          <td>0.2984</td>
          <td>0.7259</td>
          <td>0.3162</td>
          <td>0.7173</td>
          <td>0.3008</td>
          <td>0.7221</td>
          <td>0.3126</td>
          <td>0.7224</td>
          <td>0.3136</td>
     </tr>
     <tr>
          <td>8</td>
          <td>0.7071</td>
          <td>0.2988</td>
          <td>0.7231</td>
          <td>0.3127</td>
          <td>0.7176</td>
          <td>0.3049</td>
          <td>0.7207</td>
          <td>0.3102</td>
          <td>0.7199</td>
          <td>0.3135</td>
     </tr>
     <tr>
          <td>9</td>
          <td>0.7037</td>
          <td>0.2968</td>
          <td>0.7194</td>
          <td>0.3094</td>
          <td>0.7119</td>
          <td>0.3001</td>
          <td>0.7170</td>
          <td>0.3072</td>
          <td>0.7182</td>
          <td>0.3099</td>
     </tr>
     <tr>
          <td>10</td>
          <td>0.6989</td>
          <td>0.2917</td>
          <td>0.7173</td>
          <td>0.3068</td>
          <td>0.7073</td>
          <td>0.2965</td>
          <td>0.7143</td>
          <td>0.3056</td>
          <td>0.7158</td>
          <td>0.3074</td>
     </tr>
     <tr>
          <td>11</td>
          <td>0.6953</td>
          <td>0.2905</td>
          <td>0.7146</td>
          <td>0.3046</td>
          <td>0.7035</td>
          <td>0.2954</td>
          <td>0.7080</td>
          <td>0.2986</td>
          <td>0.7126</td>
          <td>0.3069</td>
     </tr>
     <tr>
          <td>12</td>
          <td>0.6908</td>
          <td>0.2879</td>
          <td>0.7142</td>
          <td>0.3018</td>
          <td>0.6995</td>
          <td>0.2882</td>
          <td>0.7033</td>
          <td>0.2967</td>
          <td>0.7106</td>
          <td>0.3034</td>
     </tr>
</table>
