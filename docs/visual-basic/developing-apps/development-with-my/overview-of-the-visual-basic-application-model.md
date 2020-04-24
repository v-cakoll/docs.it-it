---
title: Cenni preliminari sul modello di applicazione Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976466"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Cenni preliminari sul modello di applicazione Visual Basic

Visual Basic fornisce un modello ben definito per controllare il comportamento delle applicazioni Windows Forms: il modello di applicazione Visual Basic. Questo modello include gli eventi per gestire l'avvio e l'arresto dell'applicazione, nonché gli eventi per intercettare le eccezioni non gestite. Fornisce inoltre il supporto per lo sviluppo di applicazioni a istanza singola. Il modello applicativo è estendibile, quindi gli sviluppatori che necessitano di un maggior controllo possono personalizzare i metodi sottoponibili a override.  
  
## <a name="uses-for-the-application-model"></a>Usi per il modello di applicazione  

 Un'applicazione tipica deve eseguire attività quando viene avviata e arrestata. Ad esempio, all'avvio, l'applicazione può visualizzare una schermata iniziale, stabilire connessioni al database, caricare uno stato salvato e così via. Quando l'applicazione viene arrestata, è possibile chiudere le connessioni di database, salvare lo stato corrente e così via. Inoltre, l'applicazione può eseguire codice specifico quando l'applicazione si arresta in modo imprevisto, ad esempio durante un'eccezione non gestita.  
  
 Il modello di applicazione Visual Basic semplifica la creazione di un'applicazione a *istanza singola* . Un'applicazione a istanza singola è diversa da un'applicazione normale, in quanto è possibile eseguire una sola istanza dell'applicazione alla volta. Il tentativo di avviare un'altra istanza di un'applicazione a istanza singola comporta la notifica dell'istanza originale, per mezzo dell' `StartupNextInstance` evento, che è stato eseguito un altro tentativo di avvio. La notifica include gli argomenti della riga di comando dell'istanza successiva. L'istanza successiva dell'applicazione viene quindi chiusa prima che possa verificarsi un'inizializzazione.  
  
 Viene avviata un'applicazione a istanza singola e viene verificato se si tratta della prima istanza o di un'istanza successiva dell'applicazione:  
  
- Se è la prima istanza, viene avviata come di consueto.  
  
- Ogni tentativo successivo di avviare l'applicazione, mentre viene eseguita la prima istanza, comporta un comportamento molto diverso. Il tentativo successivo invia una notifica alla prima istanza sugli argomenti della riga di comando e quindi si chiude immediatamente. La prima istanza gestisce l' `StartupNextInstance` evento per determinare quali sono gli argomenti della riga di comando dell'istanza successiva e continuano a essere eseguiti.  
  
     Questo diagramma mostra il modo in cui un'istanza successiva segnala la prima istanza:  
  
     ![Diagramma che mostra un'immagine dell'applicazione a istanza singola.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Gestendo l' `StartupNextInstance` evento, è possibile controllare il comportamento dell'applicazione a istanza singola. Microsoft Outlook, ad esempio, viene in genere eseguito come applicazione a istanza singola. Quando Outlook è in esecuzione e si tenta di riavviare Outlook, lo stato attivo passa all'istanza originale, ma non viene aperta un'altra istanza.  
  
## <a name="events-in-the-application-model"></a>Eventi nel modello applicativo  

 Nel modello di applicazione sono disponibili gli eventi seguenti:  
  
- **Avvio dell'applicazione**. L'applicazione genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> evento all'avvio. Gestendo questo evento, è possibile aggiungere il codice che Inizializza l'applicazione prima che venga caricato il form principale. L' `Startup` evento fornisce anche l'annullamento dell'esecuzione dell'applicazione durante la fase del processo di avvio, se necessario.  
  
     È possibile configurare l'applicazione in modo da visualizzare una schermata iniziale mentre viene eseguito il codice di avvio dell'applicazione. Per impostazione predefinita, il modello di applicazione elimina la schermata iniziale quando si `/nosplash` USA `-nosplash` l'argomento della riga di comando o.  
  
- **Applicazioni a istanza singola**. L' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento viene generato quando viene avviata un'istanza successiva di un'applicazione a istanza singola. L'evento passa gli argomenti della riga di comando dell'istanza successiva.  
  
- **Eccezioni non gestite**. Se l'applicazione rileva un'eccezione non gestita, genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> evento. Il gestore per l'evento può esaminare l'eccezione e determinare se continuare l'esecuzione.  
  
     In `UnhandledException` alcune circostanze l'evento non viene generato. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Modifiche della connettività di rete**. Se la disponibilità di rete del computer viene modificata, l'applicazione <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> genera l'evento.  
  
     In `NetworkAvailabilityChanged` alcune circostanze l'evento non viene generato. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- L'applicazione è stata **arrestata**. L'applicazione fornisce l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento da segnalare quando sta per essere arrestato. In tale gestore eventi, è possibile verificare che le operazioni che l'applicazione deve eseguire, ad esempio la chiusura e il salvataggio, siano completate. È possibile configurare l'applicazione in modo che venga arrestata quando il form principale viene chiuso o per arrestarsi solo quando tutti i form si chiudono.  
  
## <a name="availability"></a>Disponibilità  

 Per impostazione predefinita, il modello di applicazione Visual Basic è disponibile per i progetti Windows Forms. Se si configura l'applicazione in modo che usi un oggetto di avvio diverso o si avvia il codice dell' `Sub Main`applicazione con un oggetto personalizzato, tale oggetto o classe potrebbe dover fornire un' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> implementazione della classe per usare il modello di applicazione. Per informazioni sulla modifica dell'oggetto di avvio, vedere [pagina applicazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vedi anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
