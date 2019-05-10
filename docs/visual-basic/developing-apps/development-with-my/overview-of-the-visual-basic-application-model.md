---
title: Cenni preliminari sul modello di applicazione Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 0144c92e01e617081ae05003e6a7175c63166891
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622799"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Cenni preliminari sul modello di applicazione Visual Basic
Visual Basic fornisce un modello ben definito per il controllo del comportamento delle applicazioni Windows Forms: il modello di applicazione Visual Basic. Questo modello include gli eventi per la gestione dell'applicazione avvio e arresto, nonché gli eventi per intercettare eccezioni non gestite. Fornisce inoltre il supporto per lo sviluppo di applicazioni a istanza singola. Il modello applicativo è estensibile, in modo che gli sviluppatori che devono esercitare un controllo più possono personalizzare i relativi metodi sottoponibili a override.  
  
## <a name="uses-for-the-application-model"></a>Viene utilizzato per il modello di applicazione  
 Una tipica applicazione deve eseguire le attività quando viene avviato e arrestato. Ad esempio, all'avvio, l'applicazione può visualizzare una schermata, stabilire connessioni al database, caricare uno stato salvato e così via. Quando l'applicazione viene arrestata, è possibile chiudere le connessioni al database, salvare lo stato corrente e così via. Inoltre, l'applicazione può eseguire codice specifico quando l'applicazione venga interrotto improvvisamente, ad esempio durante un'eccezione non gestita.  
  
 Il modello di applicazione Visual Basic semplifica creare un *a istanza singola* dell'applicazione. Un'applicazione a istanza singola è diverso da una normale applicazione in cui è possibile essere in esecuzione solo un'istanza dell'applicazione alla volta. Un tentativo di avviare un'altra istanza di un'applicazione a istanza singola risulta nell'istanza originale, inviare una notifica, ovvero per mezzo del `StartupNextInstance` eventi, che è stato effettuato un altro tentativo di avvio. La notifica include argomenti della riga di comando dell'istanza successiva. L'istanza successiva dell'applicazione viene quindi chiusa prima di poter eseguire qualsiasi inizializzazione.  
  
 Un'applicazione a istanza singola viene avviato e verifica se si tratta della prima istanza o un'istanza successiva dell'applicazione:  
  
- Se è la prima istanza, inizia come di consueto.  
  
- Ogni successivo tentativo di avviare l'applicazione, mentre la prima istanza è in esecuzione, comporta un comportamento molto diverso. Il tentativo successivo notifica la prima istanza sugli argomenti della riga di comando e quindi chiude immediatamente. La prima istanza gestisce il `StartupNextInstance` individuare gli argomenti della riga di comando dell'istanza successiva e continua l'esecuzione dell'evento.  
  
     Questo diagramma mostra come un'istanza successiva segnala la prima istanza:  
  
     ![Diagramma che mostra l'immagine di un'applicazione di istanza singola.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Gestendo i `StartupNextInstance` evento, è possibile controllare il comportamento dell'applicazione a istanza singola. Ad esempio, Microsoft Outlook in genere viene eseguito come un'applicazione a istanza singola. Quando Outlook è in esecuzione e si prova ad avviare Outlook anche in questo caso, lo stato attivo passa all'istanza originale ma non si apre un'altra istanza.  
  
## <a name="events-in-the-application-model"></a>Eventi nel modello di applicazione  
 Gli eventi seguenti sono disponibili nel modello di applicazione:  
  
- **Avvio dell'applicazione**. L'applicazione genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> eventi all'avvio. Se si gestisce questo evento, è possibile aggiungere il codice che inizializza l'applicazione prima del caricamento del form principale. Il `Startup` eventi consente anche di annullare l'esecuzione dell'applicazione durante tale fase del processo di avvio, se necessario.  
  
     È possibile configurare l'applicazione per visualizzare una schermata mentre è in esecuzione il codice di avvio dell'applicazione. Per impostazione predefinita, il modello di applicazione elimina la schermata iniziale dello schermo quando sia la `/nosplash` o `-nosplash` viene utilizzato l'argomento della riga di comando.  
  
- **Le applicazioni a istanza singola**. Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento viene generato quando viene avviata una seconda istanza di un'applicazione a istanza singola. L'evento passa gli argomenti della riga di comando dell'istanza successiva.  
  
- **Le eccezioni non gestite**. Se l'applicazione rileva un'eccezione non gestita, genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> evento. Il gestore dell'evento è possibile esaminare l'eccezione e stabilire se continuare l'esecuzione.  
  
     Il `UnhandledException` evento non viene generato in alcune circostanze. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Modifiche di connettività di rete**. Se viene modificata la disponibilità della rete del computer, l'applicazione genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> evento.  
  
     Il `NetworkAvailabilityChanged` evento non viene generato in alcune circostanze. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Chiusura dell'applicazione**. L'applicazione fornisce il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento per segnalare quando sta per arrestare. In tal caso, gestore di è possibile assicurarsi che le operazioni dell'applicazione deve eseguire, ovvero la chiusura e il salvataggio, ad esempio, vengono completate. È possibile configurare l'applicazione arresta alla chiusura del form principale, o per arrestare solo quando tutti i form chiuso.  
  
## <a name="availability"></a>Disponibilità  
 Per impostazione predefinita, il modello di applicazione Visual Basic è disponibile per i progetti Windows Form. Se si configura l'applicazione per usare un oggetto di avvio diverse o avviare il codice dell'applicazione con una classe personalizzata `Sub Main`, oggetto o alla classe potrebbe essere necessario fornire un'implementazione del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe da utilizzare il modello di applicazione. Per informazioni sulla modifica dell'oggetto di avvio, vedere [pagina dell'applicazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
