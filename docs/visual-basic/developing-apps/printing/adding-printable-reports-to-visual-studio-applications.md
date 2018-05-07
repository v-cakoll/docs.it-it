---
title: Aggiunta di rapporti stampabili ad applicazioni Visual Studio
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 4a7275a665e0c3290c2b3cd55c1af0c7cf0504f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Aggiunta di rapporti stampabili ad applicazioni Visual Studio
Visual Studio supporta un'ampia gamma di soluzioni di report che consentono di aggiungere report per le applicazioni Visual Basic di dati avanzati. È possibile creare e aggiungere i report utilizzando i controlli ReportViewer, Crystal Reports o SQL Server Reporting Services.  
  
> [!NOTE]
>  SQL Server Reporting Services fa parte di SQL Server 2005 anziché Visual Studio. In Reporting Services non installato nel sistema, a meno che non è installato SQL Server 2005.  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Panoramica di Microsoft Reporting tecnologia nelle applicazioni Visual Basic  
 Per utilizzare una tecnologia nell'applicazione di report di Microsoft, scegliere uno degli approcci seguenti:  
  
-   Aggiungere uno o più istanze di un controllo ReportViewer a un'applicazione Windows di Visual Basic.  
  
-   Integrare SQL Server Reporting Services a livello di codice vengono eseguite mediante chiamate al servizio Web ReportServer.  
  
-   Utilizzare il controllo ReportViewer e Microsoft SQL Server 2005 Reporting Services insieme, utilizzando il controllo come visualizzatore di report e un server di report come un elaboratore di report. Si noti che, se si desidera utilizzare un server di report e il controllo ReportViewer insieme, è necessario utilizzare la versione di SQL Server 2005 Reporting Services.  
  
## <a name="using-reportviewer-controls"></a>Utilizzo dei controlli ReportViewer  
 Il modo più semplice per incorporare la funzionalità di report in un'applicazione Windows di Visual Basic consiste nell'aggiungere il controllo ReportViewer a un form nell'applicazione. Il controllo aggiunge direttamente all'applicazione funzionalità di elaborazione di report e fornisce una finestra di progettazione report integrata in modo che è possibile compilare report utilizzando dati da qualsiasi oggetto dati ADO.NET. Un'API completa fornisce l'accesso programmatico al controllo e i report in modo che sia possibile configurare le funzionalità di runtime.  
  
 ReportViewer fornisce l'elaborazione del report predefiniti e la visualizzazione di funzionalità in un controllo dati singolo, distribuibile. Scegliere i che controlli ReportViewer se sono necessarie le seguenti funzionalità di report:  
  
-   Elaborazione di report nell'applicazione client. Un report elaborato viene visualizzata in un'area di visualizzazione fornita dal controllo.  
  
-   Associazione di dati alle tabelle di dati ADO.NET. È possibile creare report che utilizzano <xref:System.Data.DataTable> istanze fornite al controllo. È anche possibile associare direttamente a oggetti business.  
  
-   Controlli ridistribuibili che è possibile includere nell'applicazione.  
  
-   Funzionalità di runtime, ad esempio navigazione tra le pagine, la stampa, la ricerca e formati di esportazione. Una barra degli strumenti di ReportViewer fornisce supporto per queste operazioni.  
  
 Per utilizzare il controllo ReportViewer, è possibile trascinarlo dal **dati** sezione degli strumenti Visual Studio in un form nell'applicazione Windows di Visual Basic.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>Creazione di report in Visual Studio per i controlli ReportViewer  
 Per compilare un report eseguito in ReportViewer, aggiungere un **Report** modello al progetto. Visual Studio crea un file di definizione report client (con estensione rdlc), il file viene aggiunto al progetto e apre una finestra di progettazione report integrata nell'area di lavoro di Visual Studio.  
  
 Progettazione Report di Visual Studio si integra con il **origini dati** finestra. Quando si trascina un campo da di **origini dati** finestra per il report, progettazione Report copia i metadati sull'origine dati nel file di definizione del report. Questi metadati vengono utilizzati dal controllo ReportViewer per generare automaticamente il codice di associazione dati.  
  
 Progettazione Report di Visual Studio non include la funzionalità di anteprima. Per visualizzare in anteprima il report, eseguire l'applicazione e visualizzare in anteprima il report incorporato.  
  
|Per aggiungere funzionalità di report di base dell'applicazione|  
|---|    
|1.  Trascinare un controllo ReportViewer dal **dati** scheda della finestra di **della casella degli strumenti** nel form.<br />2.  Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**. Nel **Aggiungi nuovo elemento** la finestra di dialogo, seleziona il **Report** icona e fare clic su **Aggiungi**.<br />     Verrà visualizzata la finestra di progettazione di Report nell'ambiente di sviluppo e un file di report (con estensione rdlc) viene aggiunto al progetto.<br />3.  Trascinare gli elementi del report dal **della casella degli strumenti** nel layout del report e disporli nel modo desiderato.<br />4.  Trascinare i campi dal **origini dati** finestra per gli elementi del report nel layout del report.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Utilizzo di Reporting Services nelle applicazioni Visual Basic  
 Reporting Services è una tecnologia di creazione di report basato su server fornita con SQL Server. Reporting Services include funzionalità aggiuntive non disponibili nei controlli ReportViewer. Scegliere Reporting Services se si necessita di una delle seguenti funzionalità:  
  
-   Distribuzione con scalabilità orizzontale e l'elaborazione del report sul lato server che offre prestazioni migliori per i report complessi o con esecuzione prolungata e per l'attività di report con volumi elevati.  
  
-   Formati di output dei dati integrati e l'elaborazione del report, con supporto per controlli report personalizzati e avanzate per il rendering.  
  
-   Pianificare l'elaborazione del report in modo che è possibile specificare esattamente quando i report vengono eseguiti.  
  
-   Distribuzione di report basato su sottoscrizione tramite posta elettronica o a percorsi di condivisione file.  
  
-   Il reporting ad hoc in modo che gli utenti di business possono creare report in base alle esigenze.  
  
-   Sottoscrizioni guidate dai dati che indirizzare l'output del report personalizzato a un elenco dinamico di destinatari.  
  
-   Estensioni personalizzate per l'elaborazione dati, il recapito del report, l'autenticazione personalizzata e il rendering del report.  
  
 Il server di report viene implementato come servizio Web. Il codice dell'applicazione deve includere le chiamate al servizio Web per accedere ai report e altri metadati. Il servizio Web fornisce accesso a livello di codice completo per un'istanza del server di report.  
  
 Poiché Reporting Services è una tecnologia di creazione di report basata sul Web, il visualizzatore predefinito Mostra i report che vengono eseguito il rendering in formato HTML. Se non si desidera utilizzare HTML come formato di presentazione del report predefinito, è necessario scrivere un visualizzatore di report personalizzato per l'applicazione.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Creazione di report in Visual Studio per Reporting Services  
 Per compilare i report eseguiti in un server di report, creare definizione del report (con estensione rdl) file in Visual Studio tramite Business Intelligence Development Studio, incluso in SQL Server 2005.  
  
> [!NOTE]
>  È necessario disporre di SQL Server 2005 installato per utilizzare SQL Server Reporting Services e Business Intelligence Development Studio.  
  
 Business Intelligence Development Studio aggiunge modelli di progetto che sono specifici dei componenti di SQL Server. Per creare report, è possibile scegliere tra la **progetto Server Report** o **Creazione guidata progetto Server di Report** modelli. È possibile specificare le connessioni alle origini dati e query per un'ampia gamma di tipi di origine dati, inclusi SQL Server, Oracle, Analysis Services, XML e SQL Server Integration Services. Oggetto **dati** scheda **Layout** scheda e **anteprima** scheda consentono di definire i dati, creare un layout del report e visualizzare in anteprima dei report nella stessa area di lavoro.  
  
 Le definizioni compilazione per il controllo o il server di report può essere riutilizzato in entrambe le tecnologie di report.  
  
|Per creare un report eseguito in un server di report|  
|---|    
|1.  Nel **File** menu, scegliere **New**.<br />     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .<br />2.  Nel **tipi di progetto** riquadro, fare clic su **progetti Business Intelligence**.<br />3.  Nel riquadro Modelli selezionare **progetto Server Report** o **Creazione guidata progetto Server di Report**.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>Utilizzo di controlli ReportViewer e SQL Server Reporting Services insieme  
 I controlli ReportViewer e SQL Server 2005 Reporting Services possono essere utilizzate insieme nella stessa applicazione.  
  
-   Il controllo ReportViewer fornisce un visualizzatore che viene utilizzato per visualizzare i report nell'applicazione.  
  
-   Reporting Services fornisce i report e consente di eseguire tutta l'elaborazione in un server remoto.  
  
 Il controllo ReportViewer può essere configurato per visualizzare i report archiviati ed elaborati in un server di report di Reporting Services remoto. Questo tipo di configurazione è denominato *modalità di elaborazione remota*. In modalità di elaborazione remota il controllo richiede un report che viene archiviato in un server di report remoto. Il server di report esegue tutte l'elaborazione del report, l'elaborazione dati e il rendering del report. Un report eseguito il rendering viene restituito al controllo e visualizzato nell'area di visualizzazione.  
  
 I report eseguiti su un supporto di server di report aggiuntivo formati di esportazione, dispone di un'implementazione di parametrizzazione di report diverso, utilizzare i tipi di origine dati che sono supportati dal server di report e si accede tramite il modello di autorizzazione basata sui ruoli nel server di report.  
  
 Per utilizzare la modalità di elaborazione remota, specificare l'URL e il percorso di un server di report quando si configura il controllo ReportViewer.
