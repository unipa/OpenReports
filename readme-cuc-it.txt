17/11/2011
 
Aggiornamento Birt dalla versione 2.3.2 alla versione 3.7.1 
	1) Eliminate su web-inf\lib le librerie con prefisso birt-2.3.2 
	2) Eliminata la directory platform da web-inf
	3) Aggiunte su web-inf\lib le librerie con prefisso birt-3.7.1 prelevate da birt-runtime-3_7_1\ReportEngine\lib

-Aggiunta la gestione dei Pool di connessione per i report generati da Birt

	1) modificato il metodo handleDataSourceOverrides della classe BirtReportEngine

-Aggiunta la generazione di file DOC, PPT, ODT, ODS, ODP, PS, CSV per i report generati con Birt:

	1) Modificato l'oggetto di dominio Report e la relativa tabella sul database con i nuovi campi: 
		  pptExportEnabled/PPT_EXPORT, odtExportEnabled/ODT_EXPORT, 
		  odsExportEnabled/ODS_EXPORT, odpExportEnabled/ODP_EXPORT, 
		  psExportEnabled/PS_EXPORT, htmlEmbeddedExportEnabled/HTML_EMBEDDED_EXPORT  
	
	2) Aggiunte le costanti CONTENT_TYPE_DOC,CONTENT_TYPE_PPT,CONTENT_TYPE_ODT,CONTENT_TYPE_ODS,CONTENT_TYPE_ODP,CONTENT_TYPE_PS in org/efs/openreports/engine/output/ReportEngineOutput.java
	3) Modificato il metodo getContentExtension in org/efs/openreports/engine/output/ReportEngineOutput.java
	4) Modificato il metodo generateReport in org/efs/openreports/engine/BirtReportEngine.java
	5) Modificato ReportOptions.jsp	
	6) Modificato EditReportAction EditReport.jsp
	
	
-Eliminato il package org\apache\commons\io\  dalla libreria birt-3.7.1-org.apache.batik.pdf_1.6.0.v201105071520.jar che collideva con commons-io-1.3.1.jar	mandando in eccezione l'upload dei file