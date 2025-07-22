html:
	pandoc ChasteBase-Table.md -o body.html
	echo -e \<\!DOCTYPE html\> > ChasteBase.html
	echo -e \<html\> > ChasteBase.html
	cat ChasteBase-Table-Head.html >> ChasteBase.html
	echo -e \<body\> >> ChasteBase.html
	cat body.html >> ChasteBase.html
	echo -e \</body\> >> ChasteBase.html
html-s:
	pandoc ChasteBase-Table.md -o ChasteBase.html -s --metadata title="ChasteBase" --metadata subtitle="A plain text Chess Database" --metadata author="Chastity White Rose"
