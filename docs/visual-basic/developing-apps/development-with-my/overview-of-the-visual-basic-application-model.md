---
title: Cenni preliminari sul modello di applicazione Visual Basic
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b0e01317a6dab18ea03047c146def32b5675ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="overview-of-the-visual-basic-application-model"></a>Cenni preliminari sul modello di applicazione Visual Basic
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce un modello ben definito per il controllo del comportamento delle applicazioni Windows Forms: il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] modello dell'applicazione. Questo modello include eventi per la gestione dell'applicazione avvio e arresto, nonché degli eventi per intercettare eccezioni non gestite. Fornisce inoltre supporto per lo sviluppo di applicazioni a istanza singola. Il modello di applicazione è estensibile, pertanto gli sviluppatori che necessita di maggiore controllo possono personalizzare i relativi metodi sottoponibili a override.  
  
## <a name="uses-for-the-application-model"></a>Viene utilizzato per il modello di applicazione  
 Una tipica applicazione deve eseguire le attività quando viene avviato e arrestato. Ad esempio, all'avvio, l'applicazione può visualizzare una schermata, stabilire connessioni al database, caricare uno stato salvato e così via. Quando l'applicazione viene chiusa, può chiudere le connessioni di database, salvare lo stato corrente e così via. Inoltre, l'applicazione può eseguire codice specifico quando l'applicazione venga interrotto improvvisamente, ad esempio durante un'eccezione non gestita.  
  
 Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] modello dell'applicazione consente di creare facilmente un *a istanza singola* dell'applicazione. Un'applicazione a istanza singola è diverso da un'applicazione normale che è possibile eseguire solo un'istanza dell'applicazione alla volta. Un tentativo di avviare un'altra istanza di un'applicazione a istanza singola risulta nell'istanza originale viene inviata una notifica, mediante il `StartupNextInstance` evento, che è stato effettuato un altro tentativo di avvio. La notifica include argomenti della riga di comando dell'istanza successiva. La seconda istanza dell'applicazione viene quindi chiusa prima di poter eseguire qualsiasi inizializzazione.  
  
 Un'applicazione a istanza singola avvia e controlla se è la prima istanza o la seconda istanza dell'applicazione:  
  
-   Se è la prima istanza, viene avviato come di consueto.  
  
-   Ogni successivo tentativo di avviare l'applicazione, mentre la prima istanza è in esecuzione, comporta un comportamento molto diverso. Il tentativo successivo è la prima istanza sugli argomenti della riga di comando di notifica e quindi chiude immediatamente. La prima istanza gestisce il `StartupNextInstance` evento per determinare gli argomenti della riga di comando dell'istanza successiva e continua a essere eseguito.  
  
     Questo diagramma viene illustrato come una seconda istanza segnala la prima istanza.  
  
     ![Immagine dell'applicazione istanza singola](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Gestendo il `StartupNextInstance` evento, è possibile controllare il comportamento dell'applicazione a istanza singola. Ad esempio, Microsoft Outlook in genere viene eseguito come un'applicazione a istanza singola. Quando Outlook è in esecuzione e si tenta di avviare Outlook anche lo stato attivo passa all'istanza originale ma non è possibile aprire un'altra istanza.  
  
## <a name="events-in-the-application-model"></a>Eventi del modello di applicazione  
 Nel modello di applicazione sono disponibili i seguenti eventi:  
  
-   **Avvio dell'applicazione**. L'applicazione genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> evento all'avvio. La gestione dell'evento, è possibile aggiungere codice che inizializza l'applicazione prima di carica il form principale. Il `Startup` eventi consente anche di annullare l'esecuzione dell'applicazione durante la fase del processo di avvio, se necessario.  
  
     È possibile configurare l'applicazione per visualizzare una schermata durante l'esecuzione di codice di avvio dell'applicazione. Per impostazione predefinita, il modello di applicazione elimina la schermata iniziale quando sia il `/nosplash` o `-nosplash` viene utilizzato l'argomento della riga di comando.  
  
-   **Applicazioni a istanza singola**. Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento viene generato quando viene avviata una seconda istanza di un'applicazione a istanza singola. L'evento passa gli argomenti della riga di comando della seconda istanza.  
  
-   **Le eccezioni non gestite**. Se l'applicazione rileva un'eccezione non gestita, genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> evento. Il gestore per l'evento è possibile esaminare l'eccezione e determinare se continuare l'esecuzione.  
  
     Il `UnhandledException` non viene generato in alcune circostanze. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Le modifiche della connettività di rete**. Se viene modificata la disponibilità di rete del computer, l'applicazione genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> evento.  
  
     Il `NetworkAvailabilityChanged` non viene generato in alcune circostanze. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Chiusura dell'applicazione**. L'applicazione fornisce il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento per segnalare quando è in fase di chiusura. In tal caso gestore, è possibile assicurarsi che le operazioni dell'applicazione deve eseguire, la chiusura e il salvataggio, ad esempio, vengono completate. È possibile configurare l'applicazione di arrestare il computer alla chiusura del form principale, o l'arresto solo tutti i moduli di chiusura.  
  
## <a name="availability"></a>Disponibilità  
 Per impostazione predefinita, il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] modello applicativo è disponibile per i progetti Windows Form. Se si configurare l'applicazione per utilizzare un oggetto di avvio diverse, o il codice dell'applicazione con un oggetto personalizzato `Sub Main`, oggetto o alla classe potrebbe essere necessario fornire un'implementazione del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe per utilizzare il modello di applicazione. Per informazioni sulla modifica dell'oggetto di avvio, vedere [pagina applicazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
