---
title: Aggiunta di rapporti stampabili ad applicazioni Visual Studio
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 65264deea3aeff1a633ea6888b3f175031b7fba5
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212014"
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Aggiunta di rapporti stampabili ad applicazioni Visual Studio
Visual Studio supporta un'ampia gamma di soluzioni di report che consentono di aggiungere report alle applicazioni Visual Basic di dati avanzati. È possibile creare e aggiungere i report mediante i controlli ReportViewer, Crystal Reports o SQL Server Reporting Services.  

  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Panoramica di Microsoft Reporting tecnologia nelle applicazioni Visual Basic  
 Scegliere uno degli approcci seguenti per usare una tecnologia nell'applicazione di reporting Microsoft:  
  
-   Aggiungere uno o più istanze di un controllo ReportViewer a un'applicazione Windows di Visual Basic.  
  
-   Integrare SQL Server Reporting Services a livello di codice vengono eseguite mediante chiamate al servizio Web ReportServer.  
  
-   Usare il controllo ReportViewer e Microsoft SQL Server 2005 Reporting Services insieme, utilizzando il controllo come un visualizzatore di report e un server di report come un elaboratore di report. (Si noti che è necessario usare la versione di SQL Server 2005 di Reporting Services se si desidera usare un server di report e il controllo ReportViewer insieme).  
  
## <a name="using-reportviewer-controls"></a>Tramite i controlli ReportViewer  
 Il modo più semplice per incorporare la funzionalità di report in un'applicazione Visual Basic Windows consiste nell'aggiungere il controllo ReportViewer a un form nell'applicazione. Il controllo consente di aggiungere direttamente all'applicazione funzionalità di elaborazione del rapporto e fornisce una progettazione report integrata in modo che è possibile compilare report usando dati da qualsiasi oggetto di dati ADO.NET. Un'API completa fornisce l'accesso programmatico al controllo e report in modo che sia possibile configurare funzionalità di run-time.  
  
 In ReportViewer sono disponibili l'elaborazione del report predefiniti e la visualizzazione di funzionalità in un controllo dati singolo e distribuito gratuitamente. Scegliere i che controlli ReportViewer, se è necessaria la funzionalità di report seguenti:  
  
-   Elaborazione di report nell'applicazione client. Viene visualizzato un rapporto elaborato in un'area di visualizzazione fornita dal controllo.  
  
-   Associazione di dati alle tabelle di dati ADO.NET. È possibile creare report che utilizzano <xref:System.Data.DataTable> istanze fornite al controllo. È anche possibile associare direttamente agli oggetti business.  
  
-   Controlli ridistribuibili che è possibile includere nell'applicazione.  
  
-   Funzionalità di runtime, ad esempio la navigazione, la stampa, la ricerca e i formati di esportazione. Una barra degli strumenti di ReportViewer fornisce supporto per queste operazioni.  
  
 Per usare il controllo ReportViewer, è possibile trascinarlo dal **dati** sezione Visual Studio Toolbox in un form nell'applicazione Windows di Visual Basic.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>Creazione di report in Visual Studio per i controlli ReportViewer  
 Per compilare un report eseguito in ReportViewer, aggiungere un **Report** modello al progetto. Visual Studio crea un file di definizione di rapporto client (con estensione rdlc), il file aggiunto al progetto e apre una finestra di progettazione report integrata nell'area di lavoro di Visual Studio.  
  
 Progettazione rapporto di Visual Studio si integra con il **Zdroje dat** finestra. Quando si trascina un campo dal **Zdroje dat** finestra per il report, progettazione Report consente di copiare i metadati relativi a origine dati nel file di definizione del report. Questi metadati vengano usato dal controllo ReportViewer per generare automaticamente codice di associazione dati.  
  
 Progettazione rapporto di Visual Studio non include funzionalità di anteprima dei report. Per visualizzare in anteprima il report, eseguire l'applicazione e visualizzare in anteprima il report incorporato.  
  
|Per aggiungere funzionalità di report di base per l'applicazione|  
|---|    
|1.  Trascinare un controllo ReportViewer dal **Data** scheda della finestra di **della casella degli strumenti** nel form.<br />2.  Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**. Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **Report** icona e fare clic su **Add**.<br />     Verrà visualizzata la finestra di progettazione di Report nell'ambiente di sviluppo e un file di report (con estensione rdlc) viene aggiunto al progetto.<br />3.  Trascinare gli elementi del report dal **casella degli strumenti** al layout del report e disporli nel modo desiderato.<br />4.  Trascinare i campi dal **Zdroje dat** finestra per gli elementi del report nel layout del report.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Utilizzo di Reporting Services nelle applicazioni Visual Basic  
 Reporting Services è una tecnologia di creazione di report basata su server fornita con SQL Server. Reporting Services include funzionalità aggiuntive non presenti nei controlli ReportViewer. Scegliere Reporting Services se si necessita di una delle funzionalità seguenti:  
  
-   Distribuzione con scalabilità orizzontale e l'elaborazione del report sul lato server che offre prestazioni migliori per i report complessi o con esecuzione prolungata e per attività di report con volumi elevati.  
  
-   Formati di output dei dati integrata e l'elaborazione del report, con supporto per controlli report personalizzati e avanzati per il rendering.  
  
-   Pianificare l'elaborazione del report in modo che sia possibile specificare esattamente quando i report vengono eseguiti.  
  
-   Distribuzione di report basato sul sottoscrittore tramite posta elettronica o a percorsi di condivisione file.  
  
-   Il reporting ad hoc in modo che gli utenti aziendali possono creare report in base alle esigenze.  
  
-   Sottoscrizioni guidate dai dati che indirizzare l'output del report personalizzato a un elenco dinamico di destinatari.  
  
-   Estensioni personalizzate per l'elaborazione dei dati, recapito di report, l'autenticazione personalizzata e il rendering del report.  
  
 Il server di report viene implementato come servizio Web. Il codice dell'applicazione deve includere le chiamate al servizio Web per accedere ai report e altri metadati. Il servizio Web fornisce accesso a livello di codice completo per un'istanza del server di report.  
  
 Poiché Reporting Services è una tecnologia di creazione report basato sul Web, il visualizzatore predefinito Mostra i report che vengono eseguito il rendering in formato HTML. Se non vuoi usare HTML come formato di presentazione del report predefinito, sarà necessario scrivere un visualizzatore di report personalizzato per l'applicazione.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Creazione di report in Visual Studio per Reporting Services  
 Per compilare i report eseguiti in un server di report, si crea definizione del report i file (con estensione rdl) in Visual Studio tramite Business Intelligence Development Studio, incluso in SQL Server 2005.  
  
 Business Intelligence Development Studio aggiunge modelli di progetto specifici di componenti di SQL Server. Per creare report, è possibile scegliere il **progetto Server di Report** oppure **Creazione guidata progetto Server Report** modelli. È possibile specificare connessioni alle origini dati e query per un'ampia gamma di tipi di origini dati, tra cui SQL Server, Oracle, Analysis Services, XML e SQL Server Integration Services. Oggetto **Data** della scheda **Layout** scheda, e **anteprima** scheda consentono di definire i dati, creare un layout di report e visualizzare in anteprima dei report nella stessa area di lavoro.  
  
 Le definizioni dei report di compilazione per il controllo o il server di report può essere riutilizzati in entrambe le tecnologie.  
  
|Per creare un report che viene eseguito in un server di report|  
|---|    
|1.  Nel **File** menu, scegliere **New**.<br />     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .<br />2.  Nel **tipi di progetto** riquadro, fare clic su **progetti Business Intelligence**.<br />3.  Nel riquadro dei modelli, selezionare **progetto Server di Report** oppure **Creazione guidata progetto Server Report**.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>Uso di controlli ReportViewer e SQL Server Reporting Services insieme  
 I controlli ReportViewer e SQL Server 2005 Reporting Services possono essere utilizzati insieme nella stessa applicazione.  
  
-   Il controllo ReportViewer fornisce un visualizzatore che consente di visualizzare i report nell'applicazione.  
  
-   Reporting Services fornisce i report ed esegue tutta l'elaborazione in un server remoto.  
  
 Il controllo ReportViewer può essere configurato per visualizzare i report archiviati ed elaborati in un server di report di Reporting Services remoto. Questo tipo di configurazione è detto *modalità di elaborazione remota*. In modalità di elaborazione remota il controllo richiede un report che viene archiviato in un server di report remoto. Il server di report esegue tutte l'elaborazione del report, l'elaborazione dati e il rendering del report. Un report eseguito il rendering viene restituito al controllo e visualizzato nell'area di visualizzazione.  
  
 Report eseguiti su un supporto di server di report aggiuntivo formati di esportazione, dispone di un'implementazione di parametrizzazione automatica di report diverso, usare i tipi di origine dati che sono supportati dal server di report e sono accessibili tramite il modello di autorizzazione basata sui ruoli nel server di report.  
  
 Per usare la modalità di elaborazione remota, specificare l'URL e il percorso di un server di report quando si configura il controllo ReportViewer.
