# Speech-Recognizer-for-other-language
Building a speech recognizer by using cmu-sphinx for all language
Step1: Install python and perl.
Step2: After the install need to cheack by using command in command prompt,
	the command is : for python = python -V 
			for perl = perl -v
Step3: For lateast sphinxbase,pocketsphinx and sphinxtrain, need visual studio 2012 or 
	newer vertion of visual studio.Install vs studio.
Step4: We need to download sphinx from their site.
	https://github.com/cmusphinx/sphinxbase
	https://github.com/cmusphinx/pocketsphinx
	https://github.com/cmusphinx/sphinxtrain
Step5: Now we need to extruct them and rebuild them and build batch file.
Step6: we need to follow the documentation from cmu-sphinx.
	https://cmusphinx.github.io/wiki/tutorialam/
Step7: we need notepad++ and cmder for showing other language.cmder actually optional.If
	your language supported normal command prompt then dont need it.
Step8: we need to change some settings in notepad++ and install TextFX plugin.For this part 	follow the video to understand how to use them.
Step9: Create nessesary file for building a acoustic model and language model or Grammer.
Step10: For language model, http://www.speech.cs.cmu.edu/tools/lmtool-new.html
	For grammer, 
	#JSGF V1.0 ISO8859-5;

	
grammar sample;
	
public <bangla> = (শূন্য | এক  | দুই | তিন | চার  | পাঁচ | ছয় | সাত | আট | নয় );

Step11: Now recording the voice and convert them wav file.you can use this site for convert
	audio file: https://audio.online-convert.com/convert-to-wav
Step12: For generating traing scripts,
	python ../sphinxtrain/scripts/sphinxtrain -t an4 setup
	and change an4 to your database name.Now configure some line in sphinx_train.cfg.
	for small amount of data,
	change the number densities from 
	$CFG_CD_TRAIN = 'no'; [165]
	$DEC_CFG_MODEL_NAME = "$CFG_EXPTNAME.ci_cont"; [242]
Step13: Now train the data, python ../sphinxtrain/scripts/sphinxtrain run
Step14: (for showing UTF-8 on console)To change the codepage for the console only, do the following:

		1. Start -> Run -> regedit
		2. Go to [HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor\Autorun]
		3. Change the value to chcp 65001
Step15: if there are any error you didnt know how to solve , just asked in cmu-sphinx 		comminuty.There are always helpful.
	https://sourceforge.net/p/cmusphinx/discussion/
