# Named Entity Recognition Using Transfer Learning
NER is a sequence tagging task, detecting entity names such as person, location, organization names, etc in a sequence of text. Real-world applications like efficient search, content recommendation, etc. uses NER. 
We chose these three applications, NER on
1. LPSC (Lunar and Planetary Science Conference)
2. BC2GM (BioCreative II Gene Mention Recognition)
3. JNLPBA(Biomedical dataset that comes from the GENIA) dataset.


## Intructions for LPSC Dataset
If you want to start from scratch, then the orginal LPSC dataset is located inside LPSC_and_BC2GM/LPSC-annotated/ folder, which is in brat annotaion format. 

## step1:
First convert it into IOB fomat, for that run the script nerToIOB.py, the input file to this should contain the path of the .txt and .ann file next to eachother. For that inside LPSC-16 and LPSC-15 use the commands
```
1. ls $PWD/*.txt > 1.list    (all the .txt file paths are in 1.list file)
2. ls $PWD/*.ann > 2.list    (all the .ann file paths are in 2.list file) 
3. paste  -d "," 1.list  2.list  > input.list   (combines the path of both .txt,.ann file with comma seperated)
```
The nertoIOB.py replaces the orginal annotaions with IOB format. 

## step2:
Convert the Brat annotation to NER format, for this download stanford core NLP package 2015-04-20 3.5.2 version from https://stanfordnlp.github.io/CoreNLP/history.html, unzip the file and after getting into the folder run the command 
```
java -Xmx5g edu.stanford.nlp.pipeline.StanfordCoreNLP -file input.txt
```

which will start the server. Now run the brat2ner.py command with input as input.list, this outputs the NER format, once the NER format is avaible, you cal close the core NLP server.

If you want to directly access the LPSC dataset in NER format it is avaible in LPSC_and_BC2GM/LPSC_dataset.

The code for NER BERT model can be run by 









