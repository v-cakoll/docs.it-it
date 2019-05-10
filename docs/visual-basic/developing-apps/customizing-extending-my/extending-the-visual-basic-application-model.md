---
title: Estensione del modello di applicazione Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: bb87879fdf584a439e09839bf4321b85e7dd6a43
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602454"
---
# <a name="extending-the-visual-basic-application-model"></a>Estensione del modello di applicazione Visual Basic
È possibile aggiungere funzionalità al modello dell'applicazione eseguendo l'override di `Overridable` i membri del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe. Questa tecnica consente di personalizzare il comportamento del modello dell'applicazione e aggiungere chiamate a metodi personalizzati come l'applicazione si avvia e arresta.  
  
## <a name="visual-overview-of-the-application-model"></a>Panoramica visiva del modello dell'applicazione  
 In questa sezione presenta visivamente la sequenza di chiamate di funzione nel modello di applicazione Visual Basic. Nella sezione successiva descrive lo scopo di ogni funzione in modo dettagliato.  
  
 L'immagine seguente mostra la sequenza di chiamate dell'applicazione del modello in un'applicazione Visual Basic Windows Form normale. La sequenza inizia quando la `Sub Main` chiamate a procedure il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> (metodo).  
  
 ![Diagramma che mostra la sequenza di chiamate di modello di applicazione.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)  
  
 Il modello di applicazione Visual Basic fornisce anche il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> e <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> eventi. L'immagine seguente mostra il meccanismo per la generazione di questi eventi.  
  
 ![Diagramma che mostra il metodo OnStartupNextInstance generando l'evento StartupNextInstance.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)  
  
 ![Diagramma che mostra il metodo OnUnhandledException generando l'evento di eccezione UnhandledException.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)  
  
## <a name="overriding-the-base-methods"></a>L'override dei metodi Base  
 Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo definisce l'ordine in cui il `Application` metodi di esecuzione. Per impostazione predefinita, il `Sub Main` procedure per un'applicazione Windows Forms viene chiamato il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> (metodo).  
  
 Se l'applicazione è una normale applicazione (più istanze dell'applicazione) o la prima istanza di un'applicazione a istanza singola, il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo viene eseguito il `Overridable` metodi nell'ordine seguente:  
  
1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. Per impostazione predefinita, questo metodo imposta gli stili di visualizzazione, gli stili di visualizzazione di testo e oggetto principal corrente per il thread principale dell'applicazione (se l'applicazione usa l'autenticazione di Windows) e chiama `ShowSplashScreen` se non si specifica `/nosplash` né `-nosplash` viene utilizzato come un argomento della riga di comando.  
  
     La sequenza di avvio dell'applicazione viene annullata se questa funzione restituisce `False`. Ciò può essere utile se non esistono circostanze in cui non eseguire l'applicazione.  
  
     Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> metodo chiama i metodi seguenti:  
  
    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Determina se l'applicazione dispone di una schermata iniziale e in caso affermativo, viene visualizzata la schermata iniziale in un thread separato.  
  
         Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> metodo contiene il codice che consente di visualizzare la schermata iniziale di schermata per almeno il numero di millisecondi specificato da di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> proprietà. Per usare questa funzionalità, è necessario aggiungere la schermata all'applicazione usando il **creazione progetti** (che imposta la `My.Application.MinimumSplashScreenDisplayTime` proprietà su due secondi), o impostare il `My.Application.MinimumSplashScreenDisplayTime` proprietà in un metodo che esegue l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> o <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> (metodo). Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Consente a una finestra di progettazione generare il codice che inizializza la schermata iniziale.  
  
         Per impostazione predefinita, questo metodo non effettua alcuna operazione. Se si seleziona una schermata iniziale per l'applicazione in Visual Basic **creazione progetti**, la finestra di progettazione esegue l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> metodo con un metodo che imposta il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> proprietà in una nuova istanza del modulo a schermata iniziale .  
  
2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Fornisce un punto di estendibilità per la generazione di `Startup` evento. La sequenza di avvio dell'applicazione viene interrotta se questa funzione restituisce `False`.  
  
     Per impostazione predefinita, questo metodo genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> evento. Se il gestore dell'evento imposta il <xref:System.ComponentModel.CancelEventArgs.Cancel> proprietà dell'argomento dell'evento al `True`, il metodo restituisce `False` per annullare l'avvio dell'applicazione.  
  
3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Fornisce il punto di partenza per quando è pronto per iniziare a eseguire dopo l'inizializzazione viene eseguita l'applicazione principale.  
  
     Per impostazione predefinita, prima che venga attivata il ciclo di messaggi Windows Form, questo metodo chiama il `OnCreateMainForm` (per creare form principale dell'applicazione) e `HideSplashScreen` (per chiudere la schermata iniziale) metodi:  
  
    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Fornisce un modo per una finestra di progettazione generare il codice che inizializza il modulo principale.  
  
         Per impostazione predefinita, questo metodo non effettua alcuna operazione. Tuttavia, quando si seleziona un modulo principale per l'applicazione in Visual Basic **creazione progetti**, esegue l'override della finestra di progettazione il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metodo con un metodo che imposta il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà in una nuova istanza del form principale.  
  
    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Se l'applicazione dispone di una schermata iniziale ed è aperto, questo metodo chiude la schermata iniziale.  
  
         Per impostazione predefinita, questo metodo chiude la schermata iniziale.  
  
4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Fornisce un modo per personalizzare il comportamento di un'applicazione a istanza singola quando viene avviata un'altra istanza dell'applicazione.  
  
     Per impostazione predefinita, questo metodo genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento.  
  
5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Fornisce un punto di estendibilità per la generazione di `Shutdown` evento. Questo metodo non viene eseguito se si verifica un'eccezione non gestita nell'applicazione principale.  
  
     Per impostazione predefinita, questo metodo genera il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento.  
  
6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Eseguito se si verifica un'eccezione non gestita in uno dei metodi sopra elencati.  
  
     Per impostazione predefinita, questo metodo genera le <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> evento fino a quando non è collegato un debugger e l'applicazione gestisce il `UnhandledException` evento.  
  
 Se l'applicazione è un'applicazione a istanza singola e l'applicazione è già in esecuzione, l'istanza successiva dell'applicazione chiama il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> metodo nell'istanza originale dell'applicazione e quindi viene chiusa.  
 
 Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> chiamate al costruttore il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà per determinare quali motore di rendering di testo da utilizzare per i form dell'applicazione. Per impostazione predefinita, il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà restituisce `False`, che indica che il motore di rendering del testo GDI utilizzabile, ovvero l'impostazione predefinita in [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. È possibile eseguire l'override di <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà da restituire `True`, che indica che verrà utilizzato il motore di rendering di testo GDI+, ovvero l'impostazione predefinita in Visual Basic .NET 2002 e Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Configurazione dell'applicazione  
 Come parte del modello di applicazione Visual Basic il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> classe fornisce proprietà protette che consentono di configurare l'applicazione. Queste proprietà devono essere impostate nel costruttore della classe di implementazione.  
  
 In un progetto Windows Forms predefinita, il **Progettazione progetti** crea codice per impostare le proprietà con le impostazioni della finestra di progettazione. Le proprietà vengono usate solo all'avvio dell'applicazione; la loro impostazione dopo l'avvio dell'applicazione non ha alcun effetto.  
  
|Proprietà|Determina|Impostazione desiderata nel riquadro dell'applicazione di creazione progetti|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Indica se l'applicazione viene eseguita come applicazione a istanza singola o più istanze.|**Rendi a istanza singola** casella di controllo|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Se l'applicazione utilizzerà gli stili di visualizzazione che corrispondono a Windows XP.|**Abilitare gli stili visivi XP** casella di controllo|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Se l'applicazione salva automaticamente le modifiche delle impostazioni utente dell'applicazione alla chiusura dell'applicazione.|**Salva My. Settings alla chiusura** casella di controllo|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Qual è la causa l'interruzione, ad esempio quando si chiude il form di avvio o quando si chiude l'ultimo modulo dell'applicazione.|**Modalità di arresto** elenco|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Cenni preliminari sul modello di applicazione Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
