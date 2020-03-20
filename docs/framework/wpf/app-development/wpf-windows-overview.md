---
title: Panoramica di Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145540"
---
# <a name="wpf-windows-overview"></a>Cenni preliminari sulle finestre WPF
Gli utenti interagiscono con le applicazioni autonome di Windows Presentation Foundation (WPF) tramite finestre. Lo scopo principale di una finestra è ospitare contenuto tramite cui visualizzare dati e permettere agli utenti di interagire con i dati. Le applicazioni WPF autonome forniscono <xref:System.Windows.Window> le proprie finestre utilizzando la classe . In questo <xref:System.Windows.Window> argomento viene presentato prima di coprire le nozioni di base per la creazione e la gestione di finestre in applicazioni autonome.  
  
> [!NOTE]
> Le applicazioni WPF ospitate da browser, incluse le [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] applicazioni browser XAML (XBAP) e le pagine sfuse, non forniscono le proprie finestre. Al contrario, sono ospitati in finestre fornite da Windows Internet Explorer. Vedere [Cenni preliminari](wpf-xaml-browser-applications-overview.md)sulle applicazioni browser XAML WPF .  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>Classe Window  
 Nella figura seguente vengono illustrate le parti costitutive di una finestra:  
  
 ![Screenshot che mostra gli elementi della finestra.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Un finestra è suddivisa in due aree: l'area non client e l'area client.  
  
 *L'area non client* di una finestra viene implementata da WPFWPF e include le parti di una finestra comuni alla maggior parte delle finestre, tra cui:  
  
- Un bordo.  
  
- Una barra del titolo.  
  
- Un'icona.  
  
- Pulsanti Riduci a icona, Ingrandisci e Ripristina.  
  
- Un pulsante Chiudi.  
  
- Un menu di sistema con voci di menu che permettono agli utenti di ridurre al minimo, ingrandire, ripristinare, spostare, ridimensionare e chiudere una finestra.  
  
 *L'area client* di una finestra è l'area all'interno dell'area non client di una finestra e viene utilizzata dagli sviluppatori per aggiungere contenuto specifico dell'applicazione, ad esempio barre dei menu, barre degli strumenti e controlli.  
  
 In WPFWPF, una finestra <xref:System.Windows.Window> è incapsulata dalla classe usata per eseguire le operazioni seguenti:In WPFWPF, a window is encapsulated by the class that you use to do the following:  
  
- Visualizzare una finestra.  
  
- Configurare dimensioni, posizione e aspetto di una finestra.  
  
- Ospitare contenuto specifico dell'applicazione.  
  
- Gestire la durata di una finestra.  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>Implementazione di una finestra  
 L'implementazione di una finestra tipica comprende sia l'aspetto che il comportamento, in cui *l'aspetto* definisce l'aspetto di una finestra per gli utenti e il *comportamento* definisce il modo in cui una finestra funziona quando gli utenti interagiscono con essa. In WPFWPF è possibile implementare l'aspetto e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il comportamento di una finestra usando il codice o il markup.  
  
 In generale, tuttavia, l'aspetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di una finestra viene implementato tramite markup e il relativo comportamento viene implementato tramite code-behind, come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Per consentire [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] l'utilizzo di un file di markup e di un file code-behind, è necessario quanto segue:  
  
- Nel markup, `Window` l'elemento `x:Class` deve includere l'attributo. Quando l'applicazione viene compilata, l'esistenza nel file `x:Class` di markup fa `partial` sì che <xref:System.Windows.Window> il motore di compilazione `x:Class` Microsoft (MSBuild) crei una classe che deriva da e ha il nome specificato dall'attributo. Ciò richiede l'aggiunta di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] una `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` dichiarazione dello spazio dei nomi XML per lo schema ( ). La `partial` classe generata implementa il `InitializeComponent` metodo , che viene chiamato per registrare gli eventi e impostare le proprietà implementate nel markup.  
  
- Nel code-behind, la classe `partial` deve essere una classe con `x:Class` lo stesso nome specificato <xref:System.Windows.Window>dall'attributo nel markup e deve derivare da . In questo modo il file code-behind da associare alla `partial` classe generata per il file di markup quando viene compilata l'applicazione (vedere Compilazione di [un'applicazione WPF](building-a-wpf-application-wpf.md)).  
  
- Nel code-behind, <xref:System.Windows.Window> la classe deve implementare un costruttore che chiama il `InitializeComponent` metodo . `InitializeComponent`viene implementato dalla classe generata `partial` dal file di markup per registrare gli eventi e impostare le proprietà definite nel markup.  
  
> [!NOTE]
> Quando si aggiunge <xref:System.Windows.Window> un nuovo al progetto <xref:System.Windows.Window> utilizzando Visual Studio, l'oggetto viene implementato utilizzando markup e code-behind e include la configurazione necessaria per creare l'associazione tra il markup e i file code-behind come descritto di seguito.  
  
 Con questa configurazione sul posto, è possibile concentrarsi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sulla definizione dell'aspetto della finestra nel markup e implementarne il comportamento nel code-behind. Nell'esempio seguente viene illustrata una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finestra con un pulsante, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> implementato nel markup e un gestore eventi per l'evento del pulsante, implementato nel code-behind.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>Configurazione di una definizione di finestra per MSBuild  
 How you implement your window determines how it is configured for MSBuild. Per una finestra definita [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzando sia markup che code-behind:For a window that is defined using both markup and code-behind:  
  
- I file di markup `Page` XAML sono configurati come elementi MSBuild.  
  
- I file code-behind sono `Compile` configurati come elementi MSBuild.  
  
 Ciò è illustrato nel file di progetto MSBuild seguente.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Per informazioni sulla compilazione di applicazioni WPF, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>Durata di una finestra  
 Come con qualsiasi classe, una finestra ha una durata che inizia alla creazione della prima istanza, dopo la quale viene aperta, attivata e disattivata e infine chiusa.  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>Apertura di una finestra  
 Per aprire una finestra, è necessario prima di tutto crearne un'istanza, come mostrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In questo esempio, viene creata un'istanza di `MarkupAndCodeBehindWindow` <xref:System.Windows.Application.Startup> l'applicazione all'avvio dell'applicazione, che si verifica quando viene generato l'evento.  
  
 Quando viene creata un'istanza di una finestra, un riferimento ad essa <xref:System.Windows.Application> viene <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>aggiunto automaticamente a un elenco di finestre gestito dall'oggetto (vedere ). Inoltre, la prima finestra di cui creare un'istanza è, per impostazione predefinita, impostata da <xref:System.Windows.Application> come finestra principale dell'applicazione (vedere <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 La finestra viene infine <xref:System.Windows.Window.Show%2A> aperta chiamando il metodo ; il risultato è illustrato nella figura seguente.  
  
 ![Finestra aperta chiamando Window.Show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Una finestra che viene <xref:System.Windows.Window.Show%2A> aperta chiamando è una finestra non modale, il che significa che l'applicazione opera in una modalità che consente agli utenti di attivare altre finestre nella stessa applicazione.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>viene chiamato per aprire finestre come finestre di dialogo in modo modale. Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo.](dialog-boxes-overview.md)  
  
 Quando <xref:System.Windows.Window.Show%2A> viene chiamato, una finestra esegue il lavoro di inizializzazione prima che venga visualizzato per stabilire l'infrastruttura che consente di ricevere l'input dell'utente. Quando la finestra viene <xref:System.Windows.Window.SourceInitialized> inizializzata, l'evento viene generato e viene visualizzata la finestra.  
  
 Come scelta <xref:System.Windows.Application.StartupUri%2A> rapida, è possibile impostare per specificare la prima finestra che viene aperta automaticamente all'avvio di un'applicazione.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 All'avvio dell'applicazione, la <xref:System.Windows.Application.StartupUri%2A> finestra specificata dal valore di viene aperta in modo non modale; internamente, la finestra viene <xref:System.Windows.Window.Show%2A> aperta chiamando il relativo metodo.  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>Proprietà della finestra  
 Una finestra aperta utilizzando <xref:System.Windows.Window.Show%2A> il metodo non ha una relazione implicita con la finestra che l'ha creata; gli utenti possono interagire con entrambe le finestre indipendentemente dall'altra, il che significa che entrambe le finestre possono eseguire le operazioni seguenti:  
  
- Coprire l'altra (a meno <xref:System.Windows.Window.Topmost%2A> che una `true`delle finestre non abbia la proprietà impostata su ).  
  
- Essere ridotte a icona, ingrandite e ripristinate senza influire sull'altra.  
  
 Alcune finestre richiedono una relazione con la finestra da cui vengono aperte. Ad esempio, un'applicazione dell'ambiente di sviluppo integrato (IDE) può aprire le finestre delle proprietà e le finestre degli strumenti il cui comportamento tipico è quello di coprire la finestra che le crea. Queste finestre devono inoltre essere chiuse, ridotte a icona, ingrandite e ripristinate insieme alla finestra da cui sono state create. Tale relazione può essere stabilita facendo *ne possedere* <xref:System.Windows.Window.Owner%2A> un'altra finestra e si ottiene impostando la proprietà della *finestra di proprietà* con un riferimento alla finestra *proprietaria.* come illustrato nell'esempio seguente.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Dopo aver stabilito la proprietà:  
  
- La finestra di proprietà può fare riferimento alla <xref:System.Windows.Window.Owner%2A> finestra proprietaria controllando il valore della relativa proprietà.  
  
- La finestra proprietaria può individuare tutte le finestre di <xref:System.Windows.Window.OwnedWindows%2A> cui è proprietario controllando il valore della relativa proprietà.  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>Impedire l'attivazione delle finestre  
 Esistono scenari in cui le finestre non devono essere attivate quando vengono visualizzate, ad esempio le finestre di conversazione di un'applicazione in stile Internet messenger o le finestre di notifica di un'applicazione di posta elettronica.  
  
 Se l'applicazione dispone di una finestra che non deve <xref:System.Windows.Window.ShowActivated%2A> essere `false` attivata <xref:System.Windows.Window.Show%2A> quando viene visualizzata, è possibile impostare la relativa proprietà su prima di chiamare il metodo per la prima volta. Di conseguenza:  
  
- La finestra non viene attivata.  
  
- L'evento <xref:System.Windows.Window.Activated> della finestra non viene generato.  
  
- La finestra attualmente attivata resta attivata.  
  
 La finestra viene attivata, tuttavia, non appena l'utente fa clic sull'area client o non client. In questo caso:  
  
- La finestra viene attivata.  
  
- Viene generato <xref:System.Windows.Window.Activated> l'evento della finestra.  
  
- La finestra precedentemente attivata viene disattivata.  
  
- La finestra <xref:System.Windows.Window.Deactivated> e <xref:System.Windows.Window.Activated> gli eventi vengono successivamente generati come previsto in risposta alle azioni dell'utente.  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>Attivazione di finestre  
 Quando una finestra viene aperta per la prima volta, <xref:System.Windows.Window.ShowActivated%2A> diventa `false`la finestra attiva (a meno che non venga visualizzata con impostato su ). La *finestra attiva* è la finestra che sta attualmente catturando l'input dell'utente, ad esempio le tracce dei tasti e i clic del mouse. Quando una finestra diventa attiva, genera l'evento. <xref:System.Windows.Window.Activated>  
  
> [!NOTE]
> Quando una finestra viene <xref:System.Windows.FrameworkElement.Loaded> aperta <xref:System.Windows.Window.ContentRendered> per la prima <xref:System.Windows.Window.Activated> volta, gli eventi e vengono generati solo dopo la creazione dell'evento. Con questo in mente, una finestra <xref:System.Windows.Window.ContentRendered> può essere effettivamente considerata aperta quando viene sollevata.  
  
 Dopo l'attivazione di una finestra, un utente può attivare un'altra finestra nella stessa applicazione oppure attivare un'altra applicazione. In questo caso, la finestra attualmente attiva <xref:System.Windows.Window.Deactivated> viene disattivata e genera l'evento. Analogamente, quando l'utente seleziona una finestra attualmente disattivata, la finestra diventa nuovamente attiva e <xref:System.Windows.Window.Activated> viene generata.  
  
 Un motivo <xref:System.Windows.Window.Activated> comune <xref:System.Windows.Window.Deactivated> per gestire ed è quello di abilitare e disabilitare le funzionalità che possono essere eseguite solo quando una finestra è attiva. Ad esempio, alcune finestre mostrano contenuto interattivo che richiede un input utente o un'attenzione costante, tra cui giochi e lettori video. L'esempio seguente è un lettore video <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> semplificato che illustra come gestire e implementare questo comportamento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Altri tipi di applicazioni possono comunque eseguire codice in background quando una finestra è disattivata. Ad esempio, un client di posta elettronica può continuare a eseguire il polling del server di posta elettronica mentre l'utente usa altre applicazioni. Applicazioni come queste forniscono un comportamento diverso o aggiuntivo mentre la finestra principale è disattivata. Riguardo al programma di posta elettronica, questo significa aggiungere il nuovo elemento di posta elettronica nella posta in arrivo e aggiungere un'icona di notifica sulla barra delle applicazioni. Un'icona di notifica deve essere visualizzata solo quando la finestra di posta <xref:System.Windows.Window.IsActive%2A> non è attiva, che può essere determinata controllando la proprietà.  
  
 Se un'attività in background viene completata, una finestra <xref:System.Windows.Window.Activate%2A> potrebbe voler notificare all'utente più urgentemente chiamando il metodo. Se l'utente interagisce con <xref:System.Windows.Window.Activate%2A> un'altra applicazione attivata quando viene chiamato, il pulsante della barra delle applicazioni della finestra lampeggia. Se un utente interagisce con l'applicazione corrente, la chiamata <xref:System.Windows.Window.Activate%2A> porterà la finestra in primo piano.  
  
> [!NOTE]
> È possibile gestire l'attivazione dell'ambito dell'applicazione utilizzando gli <xref:System.Windows.Application.Activated?displayProperty=nameWithType> eventi e <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> .  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>Chiusura di una finestra  
 La durata di una finestra si avvicina alla fine quando la finestra viene chiusa da un utente. Una finestra può essere chiusa tramite elementi nell'area non client, tra cui i seguenti:  
  
- La voce **Chiudi** del menu **Sistema.**  
  
- ALT+F4.  
  
- Premendo il pulsante **Chiudi.**  
  
 È possibile fornire un meccanismo aggiuntivo all'area client per chiudere una finestra, i più comuni dei quali includono:  
  
- Una voce **Esci** nel menu **File,** in genere per le finestre principali dell'applicazione.  
  
- Elemento **Chiudi** nel menu **File,** in genere in una finestra secondaria dell'applicazione.  
  
- Un pulsante **Annulla,** in genere in una finestra di dialogo modale.  
  
- Un pulsante **Chiudi,** in genere in una finestra di dialogo non modale.  
  
 Per chiudere una finestra in risposta a uno di questi <xref:System.Windows.Window.Close%2A> meccanismi personalizzati, è necessario chiamare il metodo . L'esempio seguente implementa la possibilità di chiudere una finestra scegliendo **Esci** dal menu **File** .  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Quando una finestra viene chiusa, <xref:System.Windows.Window.Closing> vengono <xref:System.Windows.Window.Closed>generato due eventi: e .  
  
 <xref:System.Windows.Window.Closing>viene generato prima della chiusura della finestra e fornisce un meccanismo mediante il quale è possibile impedire la chiusura della finestra. Un motivo comune per cui impedire la chiusura di una finestra è se la finestra contiene dati modificati. In questo caso, l'evento <xref:System.Windows.Window.Closing> può essere gestito per determinare se i dati sono dirty e, in caso affermativo, per chiedere all'utente se continuare a chiudere la finestra senza salvare i dati o per annullare la chiusura della finestra. Nell'esempio seguente vengono illustrati <xref:System.Windows.Window.Closing>gli aspetti chiave della gestione di .  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Al <xref:System.Windows.Window.Closing> gestore eventi <xref:System.ComponentModel.CancelEventArgs>viene passato `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> un oggetto `true` , che implementa la proprietà impostata su per impedire la chiusura di una finestra.  
  
 Se <xref:System.Windows.Window.Closing> non viene gestito o viene gestito ma non annullato, la finestra verrà chiusa. Appena prima che una <xref:System.Windows.Window.Closed> finestra si chiuda, viene sollevata. A questo punto, non è più possibile impedire la chiusura di una finestra.  
  
> [!NOTE]
> Un'applicazione può essere configurata per essere arrestata automaticamente <xref:System.Windows.Application.MainWindow%2A>alla chiusura della finestra principale dell'applicazione (vedere ) o all'ultima finestra. Per informazioni dettagliate, vedere <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Mentre una finestra può essere chiusa in modo esplicito tramite meccanismi forniti nelle aree non client e client, una finestra può anche essere chiusa in modo implicito come risultato del comportamento in altre parti dell'applicazione o di Windows, inclusi i seguenti:  
  
- Un utente si disconnette o arresta Windows.  
  
- Il proprietario di una finestra <xref:System.Windows.Window.Owner%2A>chiude (vedere ).  
  
- La finestra principale dell'applicazione è chiusa ed <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
- Viene chiamato <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
> Una volta chiusa, una finestra non può più essere riaperta.  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>Eventi di durata di una finestra  
 Nella figura seguente viene illustrata la sequenza degli eventi principali nella durata di una finestra:  
  
 ![Diagramma che mostra gli eventi nel ciclo di vita di una finestra.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 La figura seguente mostra la sequenza degli eventi principali nella durata<xref:System.Windows.Window.ShowActivated%2A> di `false` una finestra visualizzata senza attivazione (è impostata su prima che venga visualizzata la finestra):  
  
 ![Diagramma che mostra gli eventi nel ciclo di vita di una finestra senza attivazione.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>Posizione della finestra  
 Mentre è aperta, una finestra ha una posizione nelle dimensioni x e y relative al desktop. Questa posizione può essere determinata controllando le proprietà <xref:System.Windows.Window.Left%2A> e, <xref:System.Windows.Window.Top%2A> rispettivamente. È possibile impostare queste proprietà in modo da modificare la posizione della finestra.  
  
 È inoltre possibile specificare <xref:System.Windows.Window> la posizione iniziale <xref:System.Windows.Window.WindowStartupLocation%2A> di un oggetto <xref:System.Windows.WindowStartupLocation> quando viene visualizzato per la prima volta impostando la proprietà con uno dei seguenti valori di enumerazione:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (impostazione predefinita)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Se il percorso di <xref:System.Windows.WindowStartupLocation.Manual>avvio <xref:System.Windows.Window.Left%2A> <xref:System.Windows.Window.Top%2A> è specificato come <xref:System.Windows.Window> e le proprietà e non sono state impostate, verrà chiesto a Windows di visualizzare un percorso.  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>Finestre in primo piano e ordine z  
 Oltre ad avere una posizione nelle dimensioni x e y, una finestra ha anche una dimensione z, che ne determina la posizione verticale rispetto alle altre finestre. Questo concetto è noto con il nome di ordine z della finestra e ne esistono due tipi: ordine z normale e ordine z in primo piano. La posizione di una finestra *nell'ordine z normale* è determinata dal fatto che sia attualmente attiva o meno. Per impostazione predefinita, una finestra è posizionata in base all'ordine z normale. La posizione di una finestra *nell'ordine z in primo piano* è determinata anche dal fatto che sia attualmente attiva o meno. Inoltre, le finestre posizionate in base all'ordine z in primo piano si trovano sempre al di sopra di quelle posizionate in base all'ordine z normale. Una finestra si trova nell'ordine z <xref:System.Windows.Window.Topmost%2A> più `true`in alto impostandone la proprietà su .  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 In entrambi gli ordini z la finestra attualmente attiva viene visualizzata al di sopra delle altre finestre in base allo stesso ordine z.  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>Dimensioni della finestra  
 Oltre ad avere una posizione sul desktop, una finestra ha una dimensione determinata <xref:System.Windows.Window.SizeToContent%2A>da diverse proprietà, tra cui le varie proprietà width e height e .  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> e vengono utilizzati per gestire l'intervallo di larghezze che una finestra può avere durante la sua durata e vengono configurate come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 L'altezza <xref:System.Windows.FrameworkElement.MinHeight%2A>della <xref:System.Windows.FrameworkElement.Height%2A>finestra <xref:System.Windows.FrameworkElement.MaxHeight%2A>è gestita da , e , e viene configurata come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Poiché i diversi valori di larghezza e di altezza specificano ciascuno un intervallo, la larghezza e l'altezza di una finestra ridimensionabile possono corrispondere a qualsiasi valore all'interno dell'intervallo specificato per la rispettiva dimensione. Per rilevarne la larghezza <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A>l'altezza correnti, controllare rispettivamente e , .  
  
 Se si desidera che la larghezza e l'altezza della finestra abbiano una dimensione adatta <xref:System.Windows.Window.SizeToContent%2A> alle dimensioni del contenuto della finestra, è possibile utilizzare la proprietà , che ha i seguenti valori:  
  
- <xref:System.Windows.SizeToContent.Manual>. Nessun effetto (impostazione predefinita).  
  
- <xref:System.Windows.SizeToContent.Width>. Adatta alla larghezza del contenuto, che <xref:System.Windows.FrameworkElement.MinWidth%2A> ha <xref:System.Windows.FrameworkElement.MaxWidth%2A> lo stesso effetto dell'impostazione di entrambi e della larghezza del contenuto.  
  
- <xref:System.Windows.SizeToContent.Height>. Adatta all'altezza del contenuto, che <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> ha lo stesso effetto dell'impostazione di entrambi e dell'altezza del contenuto.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Adatta alla larghezza e all'altezza del <xref:System.Windows.FrameworkElement.MinHeight%2A> contenuto, che ha lo stesso effetto dell'impostazione di entrambi e <xref:System.Windows.FrameworkElement.MaxHeight%2A> dell'altezza del contenuto e dell'impostazione di entrambi <xref:System.Windows.FrameworkElement.MinWidth%2A> e <xref:System.Windows.FrameworkElement.MaxWidth%2A> sulla larghezza del contenuto.  
  
 L'esempio seguente mostra una finestra che si ridimensiona automaticamente in base al contenuto, sia in verticale sia in orizzontale, quando viene visualizzata per la prima volta.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Nell'esempio riportato di <xref:System.Windows.Window.SizeToContent%2A> seguito viene illustrato come impostare la proprietà nel codice per specificare la modalità di ridimensionamento di una finestra in base al relativo contenuto.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>Ordine di precedenza per le proprietà di ridimensionamento  
 Essenzialmente, le diverse proprietà per le dimensioni di una finestra si combinano per definire gli intervalli di larghezza e altezza per una finestra ridimensionabile. Per garantire la gestione <xref:System.Windows.Window> di un intervallo valido, valuta i valori delle proprietà size utilizzando i seguenti ordini di precedenza.  
  
 **Per le proprietà di altezza:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Per le proprietà di larghezza:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 L'ordine di precedenza può anche determinare le dimensioni di una finestra <xref:System.Windows.Window.WindowState%2A> quando viene ingrandita, che viene gestita con la proprietà .  
  
<a name="WindowState"></a>
## <a name="window-state"></a>Stato della finestra  
 Per la sua durata, una finestra ridimensionabile può avere tre stati: normale, ridotta a icona e ingrandita. Una finestra con uno stato *normale* è lo stato predefinito di una finestra. Una finestra con questo stato permette a un utente di spostarla e ridimensionarla usando un controllo di ridimensionamento o il bordo, se è ridimensionabile.  
  
 Una finestra con uno stato *ridotto* a icona <xref:System.Windows.Window.ShowInTaskbar%2A> comprime `true`il relativo pulsante della barra delle applicazioni se è impostato su ; in caso contrario, si comprime alla dimensione più piccola possibile e si sposta nell'angolo inferiore sinistro del desktop. Nessuno dei due tipi di finestra ridotta a icona può essere ridimensionato tramite un bordo o un controllo di ridimensionamento, anche se una finestra ridotta a icona non visualizzata sulla barra delle applicazioni può essere trascinata sul desktop.  
  
 Una finestra con uno stato *ingrandito* si espande fino alla dimensione massima <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>che <xref:System.Windows.Window.SizeToContent%2A> può essere, che sarà grande solo quanto le sue proprietà , e e dettate. Come per una finestra ridotta a icona, una finestra ingrandita non può essere ridimensionata tramite un controllo di ridimensionamento o trascinandone il bordo.  
  
> [!NOTE]
> I valori <xref:System.Windows.Window.Top%2A>delle <xref:System.Windows.Window.Left%2A> <xref:System.Windows.FrameworkElement.Width%2A>proprietà <xref:System.Windows.FrameworkElement.Height%2A> , , e di una finestra rappresentano sempre i valori per lo stato normale, anche quando la finestra è attualmente ingrandita o ridotta a icona.  
  
 Lo stato di una finestra può <xref:System.Windows.Window.WindowState%2A> essere configurato impostando la <xref:System.Windows.WindowState> relativa proprietà, che può avere uno dei seguenti valori di enumerazione:  
  
- <xref:System.Windows.WindowState.Normal> (impostazione predefinita)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 L'esempio seguente mostra come creare una finestra visualizzata come ingrandita quando viene aperta.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 In generale, è <xref:System.Windows.Window.WindowState%2A> necessario impostare per configurare lo stato iniziale di una finestra. Quando è visualizzata una finestra ridimensionabile, gli utenti possono premere i pulsanti Riduci a icona, Ingrandisci e Ripristina sulla barra del titolo della finestra per modificarne lo stato.  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>Aspetto della finestra  
 Per modificare l'aspetto dell'area client di una finestra, è necessario aggiungervi contenuto specifico della finestra, come pulsanti, etichette e caselle di testo. Per configurare l'area <xref:System.Windows.Window> non client, <xref:System.Windows.Window.Icon%2A> fornisce diverse proprietà, che <xref:System.Windows.Window.Title%2A> includono l'impostazione dell'icona di una finestra e per impostarne il titolo.  
  
 È anche possibile modificare l'aspetto e il comportamento del bordo dell'area non client configurando la modalità di ridimensionamento di una finestra, lo stile della finestra e se la finestra verrà o meno visualizzata come pulsante sulla barra delle applicazioni del desktop.  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>Modalità di ridimensionamento  
 A seconda <xref:System.Windows.Window.WindowStyle%2A> della proprietà, è possibile controllare come (e se) gli utenti possono ridimensionare la finestra. La scelta dello stile della finestra determina se un utente può ridimensionare la finestra trascinandone il bordo con il mouse, se i pulsanti **Riduci a icona**, **Ingrandisci**e **Ridimensiona** vengono visualizzati nell'area non client e, se vengono visualizzati, indipendentemente dal fatto che siano abilitati.  
  
 È possibile configurare la modalità <xref:System.Windows.Window.ResizeMode%2A> di ridimensionamento di una <xref:System.Windows.ResizeMode> finestra impostandone la proprietà, che può essere uno dei seguenti valori di enumerazione:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (impostazione predefinita)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Come <xref:System.Windows.Window.WindowStyle%2A>con , è improbabile che la modalità di ridimensionamento di una finestra [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cambi durante la sua durata, il che significa che molto probabilmente la si imposterà dal markup.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Si noti che è possibile rilevare se una finestra è <xref:System.Windows.Window.WindowState%2A> ingrandita, ridotta a icona o ripristinata controllando la proprietà.  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>Stile della finestra  
 Il bordo esposto dall'area non client di una finestra è adatto per la maggior parte delle applicazioni. In alcuni casi, tuttavia, sono necessari tipi di bordi diversi oppure non è necessario alcun bordo, a seconda del tipo di finestra.  
  
 Per controllare il tipo di bordo ottenuto da una finestra, impostare la relativa <xref:System.Windows.Window.WindowStyle%2A> proprietà con uno dei seguenti valori dell'enumerazione: <xref:System.Windows.WindowStyle>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (impostazione predefinita)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 L'effetto di questi stili di finestra è illustrato nella figura seguente:  
  
 ![Illustrazione degli stili dei bordi delle finestre.](./media/wpf-windows-overview/window-border-styles.png)  
  
 È possibile <xref:System.Windows.Window.WindowStyle%2A> impostare utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup o codice; perché è improbabile che cambi durante la durata di una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finestra, molto probabilmente la configurerai utilizzando il markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Stile di finestra non rettangolare  
 Ci sono anche situazioni in <xref:System.Windows.Window.WindowStyle%2A> cui gli stili di bordo che consentono di avere non sono sufficienti. Ad esempio, è possibile creare un'applicazione con un bordo non rettangolare, ad esempio utilizzato da Microsoft Windows Media Player.  
  
 Si consideri, ad esempio, la finestra a bolle di riconoscimento vocale illustrata nella figura seguente:  
  
 ![Una finestra a bolle di scorso che dice Trascinami.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Questo tipo di finestra può <xref:System.Windows.Window.WindowStyle%2A> essere <xref:System.Windows.WindowStyle.None>creato impostando la proprietà <xref:System.Windows.Window> su e utilizzando un supporto speciale che dispone di trasparenza.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Questa combinazione di valori specifica che la finestra deve essere visualizzata come completamente trasparente. In questo stato le aree di controllo (menu Chiudi, pulsanti Riduci a icona, Ingrandisci e Ripristina e così via) dell'area non client della finestra non possono essere usate. Di conseguenza, è necessario fornirne di personalizzate.  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>Presenza sulla barra delle applicazioni  

L'aspetto predefinito di una finestra include un pulsante della barra delle applicazioni, come quello illustrato nella figura seguente:

 ![Screenshot che mostra una finestra con un pulsante della barra delle applicazioni.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Alcuni tipi di finestre non dispongono di un pulsante della barra delle applicazioni, ad esempio finestre di messaggio e finestre di dialogo (vedere [Cenni preliminari sulle finestre di dialogo).](dialog-boxes-overview.md) È possibile controllare se il pulsante della barra <xref:System.Windows.Window.ShowInTaskbar%2A> delle`true` applicazioni per una finestra viene visualizzato impostando la proprietà ( per impostazione predefinita).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>Considerazioni relative alla sicurezza  
 <xref:System.Windows.Window>richiede `UnmanagedCode` l'istanza dell'autorizzazione di sicurezza. Per le applicazioni installate nel computer locale e da qui avviate, questa è inclusa nel set di autorizzazioni concesse all'applicazione.  
  
 Tuttavia, questo non rientra nel set di autorizzazioni concesse alle applicazioni avviate dall'area Internet o Intranet locale utilizzando ClickOnce. Di conseguenza, gli utenti riceveranno un avviso di sicurezza ClickOnce e dovranno elevare il set di autorizzazioni per l'applicazione all'attendibilità totale.  
  
 Inoltre, XBAP non può visualizzare finestre o finestre di dialogo per impostazione predefinita. Per una discussione sulle considerazioni relative alla sicurezza delle applicazioni autonome, vedere [Strategia](../wpf-security-strategy-platform-security.md)di sicurezza WPF - Sicurezza della piattaforma .  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>Altri tipi di finestre  
 <xref:System.Windows.Navigation.NavigationWindow>è una finestra progettata per ospitare contenuto esplorabile. Per ulteriori informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 Le finestre di dialogo sono finestre usate spesso per raccogliere informazioni da un utente in modo da completare una funzione. Ad esempio, quando un utente desidera aprire un file, la finestra di dialogo **Apri file** viene in genere visualizzata da un'applicazione per ottenere il nome del file dall'utente. Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md)
- [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)
