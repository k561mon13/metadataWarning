--------------------
metadataWarning
--------------------

Modulet læser metadata-teksten på temaer og markerer nogle udvalgte keywords, der indikerer at det er statiske data.


--------------------
INSTALLATION
--------------------

1:   Modulet ligges i ..\config\modules\custom\metadataWarning

2:  Tilføj følgende linie til modulfilen:

    <module name="metadataWarning" dir="custom/metadataWarning" permissionlevel="public"/>.

3:   Tilføj toolet til profil
	<tool module="metadataWarning" name="metadataWarning_plugin" ignore="not ModuleDefined('metadataWarning')"/>	

4:  	Scriptet indeholder en liste med keywords:
	//VIGTIGT: Af ydelseshensyn skal man kun have den korteste version af et keyword. F.eks skal man ikke have 'ikke opdateret', men kun 'ikke opd'. Det er heller ikke nødvendigt at have 'dataudtræk', hvis man bare har 'udtræk'.
	//Programmets logik skelner ikke mellem store og små bogstaver, og sørger for at markere hele ord både forud og bagud, så 'udtræk' vil også markere 'dataudtræk'. Ligeledes vil 'ej opd' også markere 'ej opdateret'.
	keywords = ['ikke ajour',
			'ikke opd',
			'udtræk',
			'ej ajour',
			'ej opd',
			'ajourføres ikke',
			'ajourføres ej',
			'opdateres ikke',
			'opdateres ej']

	scriptet indeholder desuden noget udkommenteret kode, der kan aktiveres, for også at få vist nogle symboler, der angiver om det er data fra (ekstern) service eller SQL-server