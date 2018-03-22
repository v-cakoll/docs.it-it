---
title: Creazione del servizio dati
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7d890e4c2041ae4c70a79adfc0ab4141402fcd3f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="creating-the-data-service"></a>Creazione del servizio dati
In questa attività si creerà un servizio dati di esempio che utilizza [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per esporre un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed basato sul database di esempio Northwind. L'attività è costituita dai passaggi principali seguenti:  
  
1.  Creazione di un'applicazione Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
2.  Definizione del modello di dati tramite gli strumenti di [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
3.  Aggiunta del servizio dati all'applicazione Web.  
  
4.  Abilitazione dell'accesso al servizio dati.  
  
> [!NOTE]
>  L'applicazione Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] creata al completamento di questa attività viene eseguita sul server di sviluppo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] disponibile in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Il server di sviluppo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] supporta solo l'accesso dal computer locale. Per semplificare inoltre il test del servizio dati e la risoluzione dei problemi relativi durante lo sviluppo, eseguire l'applicazione che ospita il servizio dati tramite Internet Information Services (IIS). Per altre informazioni, vedere [Procedura: sviluppare un servizio WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
### <a name="to-create-the-aspnet-web-application"></a>Per creare l'applicazione Web ASP.NET  
  
1.  In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]via il **File** dal menu **nuovo**, quindi selezionare **progetto**.  
  
2.  Nel **nuovo progetto** in presenza di una finestra di dialogo [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] selezionare il **Web** modello e quindi selezionare **applicazione Web ASP.NET**.  
  
    > [!NOTE]
    >  Se si usa [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer, sarà necessario creare un nuovo sito Web anziché una nuova applicazione Web.  
  
3.  Tipo `NorthwindService` come il nome del progetto.  
  
4.  Fare clic su **OK**.  
  
5.  (Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web. Nota: nella parte restante della guida rapida viene usato il numero di porta `12345`.  
  
    1.  In **Esplora soluzioni**, il nome del mouse il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto appena creato e quindi fare clic su **proprietà**.  
  
    2.  Selezionare il **Web** scheda e impostare il valore della **porta specifica** casella di testo `12345`.  
  
### <a name="to-define-the-data-model"></a>Per definire il modello di dati  
  
1.  In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento.**  
  
2.  Nel **Aggiungi nuovo elemento** la finestra di dialogo, fare clic su di **dati** modello e quindi selezionare **ADO.NET Entity Data Model**.  
  
3.  Per il nome del modello di dati, digitare `Northwind.edmx`.  
  
4.  Nel [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] guidata, selezionare **genera da Database**, quindi fare clic su **Avanti**.  
  
5.  Connettere il modello di dati per il database eseguendo una delle operazioni seguenti e quindi fare clic su **Avanti**:  
  
    -   Se non si dispone di una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione. Per ulteriori informazioni, vedere [procedura: creare connessioni ai database di SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631). A questa istanza di [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] deve essere collegato il database Northwind di esempio.  
  
         \- oppure -  
  
    -   Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.  
  
6.  Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.  
  
7.  Fare clic su **fine** per chiudere la procedura guidata.  
  
    > [!NOTE]
    >  Questo modello di dati generato espone le proprietà della chiave esterna sui tipi di entità. Poiché i modelli di dati creati usando [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 non includono tali proprietà, è necessario aggiornare le classi del servizio dati client di qualsiasi applicazione client creata per accedere al servizio dati Northwind creato usando [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 prima di tentare di accedere alla versione corrente del servizio dati Northwind.  
  
### <a name="to-create-the-data-service"></a>Per creare il servizio dati  
  
1.  In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento**.  
  
2.  Nel **Aggiungi nuovo elemento** nella finestra di dialogo **servizio dati WCF**.  
  
3.  Per il nome del servizio, digitare `Northwind`.  
  
     In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice. In **Esplora**, il servizio risulterà denominato Northwind con estensione. svc.cs o. svc.  
  
4.  Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`. La definizione di classe dovrà essere analoga alla seguente:  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a>Per abilitare l'accesso alle risorse del servizio dati  
  
1.  Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.  
  
    > [!NOTE]
    >  I client che possono accedere all'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] saranno inoltre in grado di accedere alle risorse esposte dal servizio dati. Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa. Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="next-steps"></a>Passaggi successivi  
 Creato un nuovo servizio dati che espone un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispone delle autorizzazioni per il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applicazione Web. Successivamente, si avvia il servizio dati da [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] e si accederà il [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed inviando richieste GET HTTP attraverso un Web browser:  
  
 [Accesso al servizio da un Web browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Strumenti di ADO.NET Entity Data Model](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
