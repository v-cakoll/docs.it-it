---
title: Estensione del modello di applicazione Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: e707f034f05aababdc70d5d6e1f9e1da0ed558bc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410231"
---
# <a name="extending-the-visual-basic-application-model"></a>Estensione del modello di applicazione Visual Basic

È possibile aggiungere funzionalità al modello di applicazione eseguendo l'override dei `Overridable` membri della <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe. Questa tecnica consente di personalizzare il comportamento del modello applicativo e di aggiungere chiamate a metodi personalizzati quando l'applicazione viene avviata e arrestata.

## <a name="visual-overview-of-the-application-model"></a>Panoramica visiva del modello applicativo

In questa sezione viene illustrata visivamente la sequenza di chiamate di funzione nel modello di applicazione Visual Basic. Nella sezione successiva viene descritto in dettaglio lo scopo di ogni funzione.

Il grafico seguente mostra la sequenza di chiamate del modello applicativo in una normale Visual Basic Windows Forms Application. La sequenza viene avviata quando la `Sub Main` routine chiama il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo.

![Diagramma che mostra la sequenza di chiamate del modello di applicazione.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Il modello di applicazione Visual Basic fornisce anche <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> gli <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> eventi e. Nella grafica seguente viene illustrato il meccanismo per la generazione di questi eventi.

![Diagramma che mostra il metodo OnStartupNextInstance che genera l'evento StartupNextInstance.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Diagramma che mostra il metodo OnUnhandledException che genera l'evento UnhandledException.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Override dei metodi di base

Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo definisce l'ordine in cui `Application` vengono eseguiti i metodi. Per impostazione predefinita, la `Sub Main` procedura per un Windows Forms Application chiama il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo.

Se l'applicazione è un'applicazione normale (applicazione a più istanze) o la prima istanza di un'applicazione a istanza singola, il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> metodo esegue i `Overridable` metodi nell'ordine seguente:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. Per impostazione predefinita, questo metodo imposta gli stili visivi, gli stili di visualizzazione del testo e l'entità corrente per il thread principale dell'applicazione (se l'applicazione usa l'autenticazione di Windows) e chiama `ShowSplashScreen` se né `/nosplash` né `-nosplash` viene usato come argomento della riga di comando.

     La sequenza di avvio dell'applicazione viene annullata se questa funzione restituisce `False` . Questa operazione può essere utile se si verificano circostanze in cui l'applicazione non deve essere eseguita.

     Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> metodo chiama i metodi seguenti:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Determina se l'applicazione dispone di una schermata iniziale definita e, in tal caso, Visualizza la schermata iniziale in un thread separato.

         Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> metodo contiene il codice che visualizza la schermata iniziale per almeno il numero di millisecondi specificato dalla <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> Proprietà. Per usare questa funzionalità, è necessario aggiungere la schermata iniziale all'applicazione usando **Progettazione progetti** (che imposta la `My.Application.MinimumSplashScreenDisplayTime` proprietà su due secondi) oppure impostare la `My.Application.MinimumSplashScreenDisplayTime` Proprietà in un metodo che esegue l'override del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> metodo o <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> . Per altre informazioni, vedere <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Consente a una finestra di progettazione di creare codice che inizializza la schermata iniziale.

         Per impostazione predefinita, questo metodo non effettua alcuna operazione. Se si seleziona una schermata iniziale per l'applicazione in **Progettazione progetti**Visual Basic, la finestra di progettazione esegue l'override del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> metodo con un metodo che imposta la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> proprietà su una nuova istanza del form della schermata iniziale.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Fornisce un punto di estendibilità per la generazione dell' `Startup` evento. La sequenza di avvio dell'applicazione si interrompe se questa funzione restituisce `False` .

     Per impostazione predefinita, questo metodo genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> evento. Se il gestore dell'evento imposta la <xref:System.ComponentModel.CancelEventArgs.Cancel> proprietà dell'argomento dell'evento su `True` , il metodo restituisce `False` per annullare l'avvio dell'applicazione.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Fornisce il punto iniziale utilizzato dall'applicazione principale quando è pronta ad avviare l'esecuzione, al termine dell'inizializzazione.

     Per impostazione predefinita, prima di immettere il Windows Forms ciclo di messaggi, questo metodo chiama `OnCreateMainForm` (per creare il form principale dell'applicazione) e `HideSplashScreen` (per chiudere la schermata iniziale) i metodi:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Consente a una finestra di progettazione di creare codice che inizializza il form principale.

         Per impostazione predefinita, questo metodo non effettua alcuna operazione. Tuttavia, quando si seleziona un form principale per l'applicazione in **Progettazione progetti**Visual Basic, la finestra di progettazione esegue l'override del <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metodo con un metodo che imposta la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> proprietà su una nuova istanza del form principale.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Se l'applicazione ha una schermata iniziale definita ed è aperta, questo metodo chiude la schermata iniziale.

         Per impostazione predefinita, questo metodo chiude la schermata iniziale.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Consente di personalizzare il comportamento di un'applicazione a istanza singola quando viene avviata un'altra istanza dell'applicazione.

     Per impostazione predefinita, questo metodo genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> evento.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Fornisce un punto di estendibilità per la generazione dell' `Shutdown` evento. Questo metodo non viene eseguito se si verifica un'eccezione non gestita nell'applicazione principale.

     Per impostazione predefinita, questo metodo genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> evento.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Eseguito se si verifica un'eccezione non gestita in uno dei metodi elencati in precedenza.

     Per impostazione predefinita, questo metodo genera l' <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> evento purché un debugger non sia collegato e l'applicazione stia gestendo l' `UnhandledException` evento.

 Se l'applicazione è un'applicazione a istanza singola e l'applicazione è già in esecuzione, l'istanza successiva dell'applicazione chiama il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> metodo sull'istanza originale dell'applicazione e quindi viene chiusa.

 Il <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> costruttore chiama la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà per determinare quale motore di rendering del testo utilizzare per i moduli dell'applicazione. Per impostazione predefinita, la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà restituisce `False` , che indica che viene utilizzato il motore di rendering del testo GDI, che è l'impostazione predefinita in Visual Basic 2005 e versioni successive. È possibile eseguire l'override della <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> proprietà per restituire `True` , che indica che viene utilizzato il motore di rendering del testo GDI+, che è l'impostazione predefinita in Visual Basic .NET 2002 e Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Configurazione dell'applicazione

 Come parte del modello di applicazione Visual Basic, la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> classe fornisce proprietà protette per la configurazione dell'applicazione. Queste proprietà devono essere impostate nel costruttore della classe di implementazione.

 In un progetto Windows Forms predefinito, **Progettazione progetti** crea codice per impostare le proprietà con le impostazioni della finestra di progettazione. Le proprietà vengono usate solo quando l'applicazione viene avviata; l'impostazione dopo l'avvio dell'applicazione non ha alcun effetto.

|Proprietà|Determina|Impostazione nel riquadro applicazione di progettazione progetti|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Indica se l'applicazione viene eseguita come applicazione a istanza singola o a più istanze.|Casella di controllo **Crea applicazione a istanza singola**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Se l'applicazione utilizzerà gli stili visivi che corrispondono a Windows XP.|Casella di controllo **Abilita stili di visualizzazione XP**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Se l'applicazione salva automaticamente le impostazioni utente dell'applicazione quando l'applicazione viene chiusa.|Casella **di controllo Salva My. Settings on Shutdown**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Cosa comporta l'interruzione dell'applicazione, ad esempio quando il modulo di avvio si chiude o quando l'ultimo form viene chiuso.|Elenco **modalità di arresto**|

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Cenni preliminari sul modello di applicazione Visual Basic](../development-with-my/overview-of-the-visual-basic-application-model.md)
- [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
