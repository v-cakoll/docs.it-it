---
title: 'Procedura: creare un servizio dati tramite un''origine dati ADO.NET Entity Framework (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9362aa6ea02f5878d2419ee7cbaab349cae27038
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] espone i dati di entità come servizio dati. Tali dati vengono forniti da [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando l'origine dati è un database relazionale. In questo argomento viene illustrato come creare un modello di dati basato su [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] in un'applicazione Web [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] in base a un database esistente e come usarlo per creare un nuovo servizio dati.  
  
 In [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] è disponibile inoltre uno strumento da riga di comando che può generare un modello di [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] all'esterno di un progetto [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente  
  
1.  Nel **progetto** menu, fare clic su **Aggiungi nuovo elemento**.  
  
2.  Nel **modelli** riquadro, fare clic su di **dati** categoria e quindi selezionare **ADO.NET Entity Data Model**.  
  
3.  Digitare il nome del modello e quindi fare clic su **Aggiungi**.  
  
     Verrà visualizzata la prima pagina della Procedura guidata [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
4.  Nel **Scegli contenuto Model** nella finestra di dialogo **genera da database**. Scegliere quindi **Avanti**.  
  
5.  Fare clic su di **nuova connessione** pulsante.  
  
6.  Nel **le proprietà di connessione** nella finestra di dialogo digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database e quindi fare clic su **OK**.  
  
     Il **Seleziona connessione dati**nella finestra di dialogo viene aggiornata con le impostazioni di connessione di database.  
  
7.  Verificare che il **Salva entità di impostazioni di connessione in App. config come:** casella di controllo è selezionata. Scegliere quindi **Avanti**.  
  
8.  Nel **Seleziona oggetti di Database** la finestra di dialogo, selezionare tutti i database di oggetti che si intende esporre nel servizio dati.  
  
    > [!NOTE]
    >  Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati. Devono essere esposti in modo esplicito mediante il servizio stesso. Per ulteriori informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Fare clic su **fine** per completare la procedura guidata.  
  
     Verrà creato un modello di dati predefinito in base al database specifico. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] consente di personalizzare il modello di dati. Per altre informazioni, vedere [Tasks](http://msdn.microsoft.com/en-us/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb) (Attività).  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Per creare il servizio dati usando il nuovo modello di dati  
  
1.  In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] aprire il file con estensione edmx che rappresenta il modello di dati.  
  
2.  Nel **Browser modello**, il modello di pulsante destro del mouse, fare clic su **proprietà**e prendere nota del nome del contenitore di entità.  
  
3.  In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento**.  
  
4.  Nel **Aggiungi nuovo elemento** nella finestra di dialogo **servizio dati WCF**.  
  
5.  Specificare un nome per il servizio e quindi fare clic su **OK**.  
  
     In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.  
  
6.  Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.  
  
7.  Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati. Per ulteriori informazioni, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Per testare il servizio dati Northwind. svc tramite un Web browser, seguire le istruzioni nell'argomento [accesso al servizio da un Browser Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Procedura: creare un servizio dati tramite il provider di reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
