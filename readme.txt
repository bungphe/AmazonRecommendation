Step1: Mo Hadoop on Virtual box, da cai san moi truong spark 1.2.1 và python 2.7
Step2: Cai đat thu vien numpy, scip
Step3: Chay lenh sau "export SPARK_HOME=/usr/hdp/2.2.4.2-2/spark" tren terminal
Step4: Chuyen 4 file AmazonALS.py, ratings.dat, products.dat, users.dat sang thu muc:
             /workspace/AmazonRecommendation cua may ao hadoop
Step5: Tao thu muc trong HDFS co dang /user/AZ_P/input, va chuyen 3 file .dat vao thu muc input vua tao bang cac lenh:
	$ hdfs dfs -mkdir /user/AZ_P/input
	$ hdfs dfs –put <file_name> <path>
Step6: Vao thu muc Demo chua file AmazonALS.py, mo terminal o đay va chay lenh:
	$ su root
	$ spark-submit AmazonALS.py <InputDirectory> <OutputFileName> <Iterations> <Partitions>
	$ spark-submit AmazonALS.py /user/AZ_P/input outputAmazonReco.dat 10 4
Step7: Mot file outputAmazonReco.dat duoc tao ra trong thu muc hien tai voi cac cot:
		userID, recommendedProduct, predictedRating
