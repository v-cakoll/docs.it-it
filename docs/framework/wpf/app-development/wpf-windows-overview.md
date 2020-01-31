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
ms.openlocfilehash: 17582192fabf85777bba250f6f53047a84f264b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742366"
---
# <a name="wpf-windows-overview"></a>Cenni preliminari sulle finestre WPF
Gli utenti interagiscono con applicazioni autonome Windows Presentation Foundation (WPF) tramite Windows. Lo scopo principale di una finestra è ospitare contenuto tramite cui visualizzare dati e permettere agli utenti di interagire con i dati. Le applicazioni WPF autonome forniscono le proprie finestre usando la classe <xref:System.Windows.Window>. Questo argomento introduce <xref:System.Windows.Window> prima di illustrare le nozioni di base relative alla creazione e alla gestione di Windows in applicazioni autonome.  
  
> [!NOTE]
> Le applicazioni WPF ospitate da browser, incluse le applicazioni browser XAML (XBAP) e le pagine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] separate, non forniscono finestre personalizzate. Sono invece ospitati in Windows fornito da Windows Internet Explorer. Vedere [Cenni preliminari sulle applicazioni browser XAML WPF](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Classe Window  
 Nella figura seguente vengono illustrate le parti costituenti di una finestra:  
  
 ![Screenshot che Mostra gli elementi della finestra.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Un finestra è suddivisa in due aree: l'area non client e l'area client.  
  
 L' *area non client* di una finestra è implementata da WPF e include le parti di una finestra comuni alla maggior parte delle finestre, incluse le seguenti:  
  
- Un bordo.  
  
- Una barra del titolo.  
  
- Un'icona.  
  
- Pulsanti Riduci a icona, Ingrandisci e Ripristina.  
  
- Un pulsante Chiudi.  
  
- Un menu di sistema con voci di menu che permettono agli utenti di ridurre al minimo, ingrandire, ripristinare, spostare, ridimensionare e chiudere una finestra.  
  
 L'area *client* di una finestra è l'area all'interno dell'area non client di una finestra e viene utilizzata dagli sviluppatori per aggiungere contenuto specifico dell'applicazione, ad esempio barre dei menu, barre degli strumenti e controlli.  
  
 In WPF, una finestra è incapsulata dalla classe <xref:System.Windows.Window> utilizzata per eseguire le operazioni seguenti:  
  
- Visualizzare una finestra.  
  
- Configurare dimensioni, posizione e aspetto di una finestra.  
  
- Ospitare contenuto specifico dell'applicazione.  
  
- Gestire la durata di una finestra.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementazione di una finestra  
 L'implementazione di una tipica finestra comprende aspetto e comportamento, in cui l' *aspetto* definisce il modo in cui una finestra esamina gli utenti e il *comportamento* definisce il modo in cui una finestra funziona mentre gli utenti interagiscono con essa. In WPF è possibile implementare l'aspetto e il comportamento di una finestra utilizzando il codice o [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 In generale, tuttavia, l'aspetto di una finestra viene implementato utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e il relativo comportamento viene implementato utilizzando code-behind, come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Per consentire l'interazione tra un file di markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e un file code-behind, è necessario quanto segue:  
  
- Nel markup, l'elemento `Window` deve includere l'attributo `x:Class`. Quando viene compilata l'applicazione, l'esistenza di `x:Class` nel file di markup fa sì che Microsoft Build Engine (MSBuild) crei una classe `partial` che deriva da <xref:System.Windows.Window> e ha il nome specificato dall'attributo `x:Class`. Questa operazione richiede l'aggiunta di una dichiarazione dello spazio dei nomi XML per lo schema di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). La classe `partial` generata implementa il metodo `InitializeComponent`, che viene chiamato per registrare gli eventi e impostare le proprietà implementate nel markup.  
  
- Nel code-behind la classe deve essere una classe `partial` con lo stesso nome specificato dall'attributo `x:Class` nel markup e deve derivare da <xref:System.Windows.Window>. Ciò consente di associare il file code-behind alla classe `partial` generata per il file di markup quando viene compilata l'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).  
  
- Nel code-behind la classe <xref:System.Windows.Window> deve implementare un costruttore che chiama il metodo `InitializeComponent`. `InitializeComponent` viene implementato dalla classe `partial` generata del file di markup per registrare gli eventi e impostare le proprietà definite nel markup.  
  
> [!NOTE]
> Quando si aggiunge un nuovo <xref:System.Windows.Window> al progetto usando Visual Studio, il <xref:System.Windows.Window> viene implementato usando markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind, come descritto qui.  
  
 Con questa configurazione, è possibile concentrarsi sulla definizione dell'aspetto della finestra in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e sull'implementazione del relativo comportamento nel code-behind. Nell'esempio seguente viene illustrata una finestra con un pulsante, implementata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, e un gestore eventi per l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del pulsante, implementato nel code-behind.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Configurazione di una definizione di finestra per MSBuild  
 La modalità di implementazione della finestra determina il modo in cui viene configurata per MSBuild. Per una finestra definita tramite il markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e il code-behind:  
  
- I file di markup XAML sono configurati come MSBuild `Page` elementi.  
  
- I file code-behind sono configurati come MSBuild `Compile` elementi.  
  
 Questa operazione viene illustrata nel file di progetto MSBuild seguente.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Per informazioni sulla compilazione di applicazioni WPF, vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Durata di una finestra  
 Come con qualsiasi classe, una finestra ha una durata che inizia alla creazione della prima istanza, dopo la quale viene aperta, attivata e disattivata e infine chiusa.  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Apertura di una finestra  
 Per aprire una finestra, è necessario prima di tutto crearne un'istanza, come mostrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In questo esempio viene creata un'istanza dell'`MarkupAndCodeBehindWindow` all'avvio dell'applicazione, che si verifica quando viene generato l'evento <xref:System.Windows.Application.Startup>.  
  
 Quando viene creata un'istanza di una finestra, un riferimento a esso viene aggiunto automaticamente a un elenco di finestre gestite dall'oggetto <xref:System.Windows.Application> (vedere <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Inoltre, la prima finestra di cui creare un'istanza è, per impostazione predefinita, impostata da <xref:System.Windows.Application> come finestra principale dell'applicazione (vedere <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 La finestra viene infine aperta chiamando il metodo <xref:System.Windows.Window.Show%2A>; il risultato è illustrato nella figura seguente.  
  
 ![Finestra aperta chiamando Window. Show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Una finestra aperta chiamando <xref:System.Windows.Window.Show%2A> è una finestra non modale, il che significa che l'applicazione funziona in una modalità che consente agli utenti di attivare altre finestre nella stessa applicazione.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A> viene chiamato per aprire Windows, ad esempio le finestre di dialogo modali. Per ulteriori informazioni, vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md) .  
  
 Quando viene chiamato <xref:System.Windows.Window.Show%2A>, una finestra esegue operazioni di inizializzazione prima che venga visualizzato per stabilire l'infrastruttura che consente di ricevere l'input dell'utente. Quando la finestra viene inizializzata, viene generato l'evento <xref:System.Windows.Window.SourceInitialized> e viene visualizzata la finestra.  
  
 In alternativa, è possibile impostare <xref:System.Windows.Application.StartupUri%2A> per specificare la prima finestra aperta automaticamente all'avvio di un'applicazione.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 All'avvio dell'applicazione, viene aperta la finestra specificata dal valore di <xref:System.Windows.Application.StartupUri%2A> maniera non modale; internamente, la finestra viene aperta chiamando il relativo metodo <xref:System.Windows.Window.Show%2A>.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Proprietà della finestra  
 Una finestra aperta usando il metodo <xref:System.Windows.Window.Show%2A> non ha una relazione implicita con la finestra che lo ha creato; Gli utenti possono interagire con entrambe le finestre indipendentemente dall'altra, il che significa che entrambe le finestre possono eseguire le operazioni seguenti:  
  
- Coprire l'altro (a meno che una delle finestre non disponga della proprietà <xref:System.Windows.Window.Topmost%2A> impostata su `true`).  
  
- Essere ridotte a icona, ingrandite e ripristinate senza influire sull'altra.  
  
 Alcune finestre richiedono una relazione con la finestra da cui vengono aperte. Ad esempio, un'applicazione IDE (Integrated Development Environment) può aprire finestre delle proprietà e finestre degli strumenti il cui comportamento tipico consiste nel coprire la finestra che le crea. Queste finestre devono inoltre essere chiuse, ridotte a icona, ingrandite e ripristinate insieme alla finestra da cui sono state create. Una relazione di questo tipo può essere stabilita impostando la proprietà di *un'altra finestra* e viene eseguita impostando la proprietà <xref:System.Windows.Window.Owner%2A> della *finestra di proprietà* con un riferimento alla *finestra proprietaria*. come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Dopo aver stabilito la proprietà:  
  
- La finestra di proprietà può fare riferimento alla finestra proprietaria controllando il valore della relativa proprietà <xref:System.Windows.Window.Owner%2A>.  
  
- Nella finestra proprietario è possibile individuare tutte le finestre di cui è proprietario controllando il valore della relativa proprietà <xref:System.Windows.Window.OwnedWindows%2A>.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Impedire l'attivazione delle finestre  
 Esistono scenari in cui Windows non deve essere attivato quando viene visualizzato, ad esempio le finestre di conversazione di un'applicazione di tipo Internet Messenger o di notifiche di un'applicazione di posta elettronica.  
  
 Se l'applicazione dispone di una finestra che non deve essere attivata quando viene visualizzata, è possibile impostare la relativa proprietà <xref:System.Windows.Window.ShowActivated%2A> su `false` prima di chiamare il metodo <xref:System.Windows.Window.Show%2A> per la prima volta. Di conseguenza:  
  
- La finestra non viene attivata.  
  
- L'evento <xref:System.Windows.Window.Activated> della finestra non viene generato.  
  
- La finestra attualmente attivata resta attivata.  
  
 La finestra viene attivata, tuttavia, non appena l'utente fa clic sull'area client o non client. In questo caso:  
  
- La finestra viene attivata.  
  
- Viene generato l'evento <xref:System.Windows.Window.Activated> della finestra.  
  
- La finestra precedentemente attivata viene disattivata.  
  
- Gli eventi <xref:System.Windows.Window.Deactivated> e <xref:System.Windows.Window.Activated> della finestra vengono generati in seguito come previsto in risposta alle azioni dell'utente.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Attivazione di finestre  
 Quando una finestra viene aperta per la prima volta, diventa la finestra attiva (a meno che non venga visualizzata con <xref:System.Windows.Window.ShowActivated%2A> impostata su `false`). La *finestra attiva* è la finestra che attualmente acquisisce l'input dell'utente, ad esempio i tratti chiave e i clic del mouse. Quando una finestra diventa attiva, genera l'evento <xref:System.Windows.Window.Activated>.  
  
> [!NOTE]
> Quando una finestra viene aperta per la prima volta, gli eventi <xref:System.Windows.FrameworkElement.Loaded> e <xref:System.Windows.Window.ContentRendered> vengono generati solo dopo la generazione dell'evento <xref:System.Windows.Window.Activated>. Tenendo presente questo aspetto, una finestra può essere considerata effettivamente aperta quando viene generato <xref:System.Windows.Window.ContentRendered>.  
  
 Dopo l'attivazione di una finestra, un utente può attivare un'altra finestra nella stessa applicazione oppure attivare un'altra applicazione. In tal caso, la finestra attualmente attiva viene disattivata e genera l'evento <xref:System.Windows.Window.Deactivated>. Analogamente, quando l'utente seleziona una finestra attualmente disattivata, la finestra diventa nuovamente attiva e viene generato <xref:System.Windows.Window.Activated>.  
  
 Un motivo comune per gestire <xref:System.Windows.Window.Activated> e <xref:System.Windows.Window.Deactivated> consiste nell'abilitare e disabilitare la funzionalità che può essere eseguita solo quando una finestra è attiva. Ad esempio, alcune finestre mostrano contenuto interattivo che richiede un input utente o un'attenzione costante, tra cui giochi e lettori video. L'esempio seguente è un lettore video semplificato che illustra come gestire <xref:System.Windows.Window.Activated> e <xref:System.Windows.Window.Deactivated> per implementare questo comportamento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Altri tipi di applicazioni possono comunque eseguire codice in background quando una finestra è disattivata. Ad esempio, un client di posta elettronica può continuare a eseguire il polling del server di posta elettronica mentre l'utente usa altre applicazioni. Applicazioni come queste forniscono un comportamento diverso o aggiuntivo mentre la finestra principale è disattivata. Riguardo al programma di posta elettronica, questo significa aggiungere il nuovo elemento di posta elettronica nella posta in arrivo e aggiungere un'icona di notifica sulla barra delle applicazioni. È necessario visualizzare un'icona di notifica solo quando la finestra posta non è attiva, che può essere determinata controllando la proprietà <xref:System.Windows.Window.IsActive%2A>.  
  
 Se un'attività in background viene completata, una finestra potrebbe voler inviare una notifica all'utente con maggiore urgenza chiamando <xref:System.Windows.Window.Activate%2A> metodo. Se l'utente sta interagendo con un'altra applicazione attivata quando viene chiamato <xref:System.Windows.Window.Activate%2A>, il pulsante della barra delle applicazioni della finestra lampeggerà. Se un utente interagisce con l'applicazione corrente, chiamando <xref:System.Windows.Window.Activate%2A> la finestra verrà portata in primo piano.  
  
> [!NOTE]
> È possibile gestire l'attivazione dell'ambito dell'applicazione usando gli eventi <xref:System.Windows.Application.Activated?displayProperty=nameWithType> e <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Chiusura di una finestra  
 La durata di una finestra si avvicina alla fine quando la finestra viene chiusa da un utente. Una finestra può essere chiusa tramite elementi nell'area non client, tra cui i seguenti:  
  
- Elemento **Chiudi** del menu di **sistema** .  
  
- ALT+F4.  
  
- Premere il pulsante **Chiudi** .  
  
 È possibile fornire un meccanismo aggiuntivo all'area client per chiudere una finestra, i più comuni dei quali includono:  
  
- Una voce di **uscita** nel menu **file** , in genere per le finestre principali dell'applicazione.  
  
- Elemento **Close** nel menu **file** , in genere in una finestra dell'applicazione secondaria.  
  
- Pulsante **Annulla** , in genere in una finestra di dialogo modale.  
  
- Un pulsante **Chiudi** , in genere in una finestra di dialogo non modale.  
  
 Per chiudere una finestra in risposta a uno di questi meccanismi personalizzati, è necessario chiamare il metodo <xref:System.Windows.Window.Close%2A>. Nell'esempio seguente viene implementata la possibilità di chiudere una finestra scegliendo **Esci** dal menu **file** .  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Quando una finestra viene chiusa, genera due eventi: <xref:System.Windows.Window.Closing> e <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> viene generato prima della chiusura della finestra e fornisce un meccanismo in base al quale è possibile impedire la chiusura della finestra. Un motivo comune per cui impedire la chiusura di una finestra è se la finestra contiene dati modificati. In questa situazione, è possibile gestire l'evento <xref:System.Windows.Window.Closing> per determinare se i dati sono sporchi e, in caso affermativo, per richiedere all'utente se continuare la chiusura della finestra senza salvare i dati o annullare la chiusura della finestra. Nell'esempio seguente vengono illustrati gli aspetti principali della gestione di <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Al gestore dell'evento <xref:System.Windows.Window.Closing> viene passato un <xref:System.ComponentModel.CancelEventArgs>, che implementa la proprietà <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> `Boolean`impostata su `true` per impedire la chiusura di una finestra.  
  
 Se <xref:System.Windows.Window.Closing> non viene gestita o viene gestita ma non annullata, la finestra verrà chiusa. Immediatamente prima della chiusura di una finestra, viene generato <xref:System.Windows.Window.Closed>. A questo punto, non è più possibile impedire la chiusura di una finestra.  
  
> [!NOTE]
> Un'applicazione può essere configurata in modo che venga arrestata automaticamente quando viene chiusa la finestra principale dell'applicazione (vedere <xref:System.Windows.Application.MainWindow%2A>) o l'ultima finestra viene chiusa. Per informazioni dettagliate, vedere <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Mentre una finestra può essere chiusa in modo esplicito tramite meccanismi forniti nelle aree client e non client, una finestra può anche essere chiusa in modo implicito come risultato del comportamento in altre parti dell'applicazione o di Windows, incluse le seguenti:  
  
- Un utente si disconnette o arresta Windows.  
  
- Il proprietario di una finestra si chiude (vedere <xref:System.Windows.Window.Owner%2A>).  
  
- La finestra principale dell'applicazione è chiusa e <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
- Chiamata del metodo <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
> Una volta chiusa, una finestra non può più essere riaperta.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Eventi di durata di una finestra  
 Nella figura seguente viene illustrata la sequenza degli eventi principali nel ciclo di vita di una finestra:  
  
 ![Diagramma che Mostra gli eventi nella durata di una finestra.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 Nella figura seguente viene illustrata la sequenza degli eventi principali nel ciclo di vita di una finestra visualizzata senza attivazione (<xref:System.Windows.Window.ShowActivated%2A> è impostata su `false` prima che venga visualizzata la finestra):  
  
 ![Diagramma che Mostra gli eventi in una durata della finestra senza attivazione.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Posizione della finestra  
 Mentre è aperta, una finestra ha una posizione nelle dimensioni x e y relative al desktop. Questo percorso può essere determinato esaminando rispettivamente le proprietà <xref:System.Windows.Window.Left%2A> e <xref:System.Windows.Window.Top%2A>. È possibile impostare queste proprietà in modo da modificare la posizione della finestra.  
  
 È anche possibile specificare la posizione iniziale di un <xref:System.Windows.Window> quando viene visualizzato per la prima volta, impostando la proprietà <xref:System.Windows.Window.WindowStartupLocation%2A> con uno dei seguenti valori di enumerazione <xref:System.Windows.WindowStartupLocation>:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (impostazione predefinita)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Se il percorso di avvio viene specificato come <xref:System.Windows.WindowStartupLocation.Manual>e le proprietà <xref:System.Windows.Window.Left%2A> e <xref:System.Windows.Window.Top%2A> non sono state impostate, <xref:System.Windows.Window> chiederà a Windows di visualizzare un percorso in.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Finestre in primo piano e ordine z  
 Oltre ad avere una posizione nelle dimensioni x e y, una finestra ha anche una dimensione z, che ne determina la posizione verticale rispetto alle altre finestre. Questo concetto è noto con il nome di ordine z della finestra e ne esistono due tipi: ordine z normale e ordine z in primo piano. La posizione di una finestra in base all' *ordine z normale* è determinata dal fatto che sia attualmente attiva o meno. Per impostazione predefinita, una finestra è posizionata in base all'ordine z normale. Il percorso di una finestra nell' *ordine z* superiore è determinato anche dal fatto che sia attualmente attivo o meno. Inoltre, le finestre posizionate in base all'ordine z in primo piano si trovano sempre al di sopra di quelle posizionate in base all'ordine z normale. Una finestra si trova nell'ordine z superiore impostando la relativa proprietà <xref:System.Windows.Window.Topmost%2A> su `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 In entrambi gli ordini z la finestra attualmente attiva viene visualizzata al di sopra delle altre finestre in base allo stesso ordine z.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Dimensioni finestra  
 Oltre a disporre di un percorso desktop, una finestra ha una dimensione determinata da diverse proprietà, incluse le varie proprietà Width e Height e <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>e <xref:System.Windows.FrameworkElement.MaxWidth%2A> vengono utilizzati per gestire l'intervallo di larghezze di una finestra durante la sua durata e vengono configurati come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 L'altezza della finestra viene gestita da <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>e <xref:System.Windows.FrameworkElement.MaxHeight%2A>e sono configurate come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Poiché i diversi valori di larghezza e di altezza specificano ciascuno un intervallo, la larghezza e l'altezza di una finestra ridimensionabile possono corrispondere a qualsiasi valore all'interno dell'intervallo specificato per la rispettiva dimensione. Per rilevare la larghezza e l'altezza correnti, controllare <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A>rispettivamente.  
  
 Se si vuole che la larghezza e l'altezza della finestra abbiano una dimensione che corrisponda alle dimensioni del contenuto della finestra, è possibile usare la proprietà <xref:System.Windows.Window.SizeToContent%2A>, che presenta i valori seguenti:  
  
- <xref:System.Windows.SizeToContent.Manual>. Nessun effetto (impostazione predefinita).  
  
- <xref:System.Windows.SizeToContent.Width>. Adattarsi alla larghezza del contenuto, che ha lo stesso effetto dell'impostazione di <xref:System.Windows.FrameworkElement.MinWidth%2A> e <xref:System.Windows.FrameworkElement.MaxWidth%2A> sulla larghezza del contenuto.  
  
- <xref:System.Windows.SizeToContent.Height>. Adatta all'altezza del contenuto, che ha lo stesso effetto dell'impostazione di <xref:System.Windows.FrameworkElement.MinHeight%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> sull'altezza del contenuto.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Adattarsi alla larghezza e all'altezza del contenuto, che ha lo stesso effetto dell'impostazione di <xref:System.Windows.FrameworkElement.MinHeight%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> sull'altezza del contenuto e dell'impostazione di <xref:System.Windows.FrameworkElement.MinWidth%2A> e <xref:System.Windows.FrameworkElement.MaxWidth%2A> sulla larghezza del contenuto.  
  
 L'esempio seguente mostra una finestra che si ridimensiona automaticamente in base al contenuto, sia in verticale sia in orizzontale, quando viene visualizzata per la prima volta.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Window.SizeToContent%2A> nel codice per specificare la modalità di ridimensionamento di una finestra per adattarla al contenuto.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Ordine di precedenza per le proprietà di ridimensionamento  
 Essenzialmente, le diverse proprietà per le dimensioni di una finestra si combinano per definire gli intervalli di larghezza e altezza per una finestra ridimensionabile. Per garantire che venga mantenuto un intervallo valido, <xref:System.Windows.Window> valuta i valori delle proprietà delle dimensioni usando gli ordini di precedenza seguenti.  
  
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
  
 L'ordine di precedenza può inoltre determinare le dimensioni di una finestra quando viene ingrandita, gestita con la proprietà <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Stato della finestra  
 Per la sua durata, una finestra ridimensionabile può avere tre stati: normale, ridotta a icona e ingrandita. Una finestra con uno stato *normale* è lo stato predefinito di una finestra. Una finestra con questo stato permette a un utente di spostarla e ridimensionarla usando un controllo di ridimensionamento o il bordo, se è ridimensionabile.  
  
 Una finestra con uno stato *ridotto a icona* viene compressa sul relativo pulsante della barra delle applicazioni se <xref:System.Windows.Window.ShowInTaskbar%2A> è impostata su `true`; in caso contrario, viene compressa alla dimensione minima possibile e viene rilocata nell'angolo inferiore sinistro del desktop. Nessuno dei due tipi di finestra ridotta a icona può essere ridimensionato tramite un bordo o un controllo di ridimensionamento, anche se una finestra ridotta a icona non visualizzata sulla barra delle applicazioni può essere trascinata sul desktop.  
  
 Una finestra con uno stato *ingrandito* si espande fino alla dimensione massima che può essere, che avrà dimensioni maggiori delle proprietà <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>e <xref:System.Windows.Window.SizeToContent%2A>. Come per una finestra ridotta a icona, una finestra ingrandita non può essere ridimensionata tramite un controllo di ridimensionamento o trascinandone il bordo.  
  
> [!NOTE]
> I valori delle proprietà <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>e <xref:System.Windows.FrameworkElement.Height%2A> di una finestra rappresentano sempre i valori per lo stato normale, anche quando la finestra è attualmente ingrandita o ridotta a icona.  
  
 Lo stato di una finestra può essere configurato impostando la relativa proprietà <xref:System.Windows.Window.WindowState%2A>, che può avere uno dei seguenti valori di enumerazione <xref:System.Windows.WindowState>:  
  
- <xref:System.Windows.WindowState.Normal> (impostazione predefinita)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 L'esempio seguente mostra come creare una finestra visualizzata come ingrandita quando viene aperta.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 In generale, è necessario impostare <xref:System.Windows.Window.WindowState%2A> per configurare lo stato iniziale di una finestra. Quando è visualizzata una finestra ridimensionabile, gli utenti possono premere i pulsanti Riduci a icona, Ingrandisci e Ripristina sulla barra del titolo della finestra per modificarne lo stato.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Aspetto della finestra  
 Per modificare l'aspetto dell'area client di una finestra, è necessario aggiungervi contenuto specifico della finestra, come pulsanti, etichette e caselle di testo. Per configurare l'area non client, in <xref:System.Windows.Window> sono disponibili diverse proprietà che includono <xref:System.Windows.Window.Icon%2A> per impostare l'icona di una finestra e <xref:System.Windows.Window.Title%2A> per impostare il titolo.  
  
 È anche possibile modificare l'aspetto e il comportamento del bordo dell'area non client configurando la modalità di ridimensionamento di una finestra, lo stile della finestra e se la finestra verrà o meno visualizzata come pulsante sulla barra delle applicazioni del desktop.  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Modalità di ridimensionamento  
 A seconda della proprietà <xref:System.Windows.Window.WindowStyle%2A>, è possibile controllare come e se gli utenti possono ridimensionare la finestra. La scelta dello stile della finestra influiscono sul fatto che un utente possa ridimensionare la finestra trascinando il bordo con il mouse, se i pulsanti **Riduci a icona**, **Ingrandisci**e **ridimensionati** vengono visualizzati nell'area non client e, se vengono visualizzati, se sono abilitati.  
  
 È possibile configurare la modalità di ridimensionamento di una finestra impostando la relativa proprietà <xref:System.Windows.Window.ResizeMode%2A>, che può essere uno dei seguenti valori di enumerazione <xref:System.Windows.ResizeMode>:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (impostazione predefinita)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Come nel caso di <xref:System.Windows.Window.WindowStyle%2A>, è improbabile che la modalità di ridimensionamento di una finestra cambi durante la sua durata, il che significa che è molto probabile che la si imposti da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Si noti che è possibile rilevare se una finestra è ingrandita, ridotta a icona o ripristinata controllando la proprietà <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Stile della finestra  
 Il bordo esposto dall'area non client di una finestra è adatto per la maggior parte delle applicazioni. In alcuni casi, tuttavia, sono necessari tipi di bordi diversi oppure non è necessario alcun bordo, a seconda del tipo di finestra.  
  
 Per controllare il tipo di bordo ottenuto da una finestra, impostare la relativa proprietà <xref:System.Windows.Window.WindowStyle%2A> con uno dei valori seguenti dell'enumerazione <xref:System.Windows.WindowStyle>:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (impostazione predefinita)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 L'effetto di questi stili di finestra è illustrato nella figura seguente:  
  
 ![Illustrazione degli stili del bordo della finestra.](./media/wpf-windows-overview/window-border-styles.png)  
  
 È possibile impostare <xref:System.Windows.Window.WindowStyle%2A> utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup o codice; Poiché è improbabile che si modifichi nel corso della durata di una finestra, è probabile che venga configurata con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Stile di finestra non rettangolare  
 Esistono anche situazioni in cui gli stili del bordo che <xref:System.Windows.Window.WindowStyle%2A> consente di avere non sono sufficienti. Ad esempio, è possibile creare un'applicazione con un bordo non rettangolare, come Microsoft Windows Media Player USA.  
  
 Si consideri, ad esempio, la finestra Bubble vocale mostrata nella figura seguente:  
  
 ![Una finestra A bolle vocale che dice trascina me.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Questo tipo di finestra può essere creato impostando la proprietà <xref:System.Windows.Window.WindowStyle%2A> su <xref:System.Windows.WindowStyle.None>e utilizzando un supporto speciale che <xref:System.Windows.Window> ha per la trasparenza.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Questa combinazione di valori specifica che la finestra deve essere visualizzata come completamente trasparente. In questo stato le aree di controllo (menu Chiudi, pulsanti Riduci a icona, Ingrandisci e Ripristina e così via) dell'area non client della finestra non possono essere usate. Di conseguenza, è necessario fornirne di personalizzate.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Presenza sulla barra delle applicazioni  

L'aspetto predefinito di una finestra include un pulsante della barra delle applicazioni, come quello illustrato nella figura seguente:

 ![Screenshot che mostra una finestra con un pulsante della barra delle applicazioni.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Alcuni tipi di finestre non dispongono di un pulsante della barra delle applicazioni, ad esempio finestre di messaggio e finestre di dialogo (vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md)). È possibile controllare se il pulsante della barra delle applicazioni per una finestra viene visualizzato impostando la proprietà <xref:System.Windows.Window.ShowInTaskbar%2A> (`true` per impostazione predefinita).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Considerazioni sulla sicurezza  
 <xref:System.Windows.Window> richiede l'autorizzazione di `UnmanagedCode` sicurezza per la creazione di istanze. Per le applicazioni installate nel computer locale e da qui avviate, questa è inclusa nel set di autorizzazioni concesse all'applicazione.  
  
 Tuttavia, non rientra nel set di autorizzazioni concesse alle applicazioni avviate da Internet o dall'area Intranet locale tramite ClickOnce. Di conseguenza, gli utenti riceveranno un avviso di sicurezza ClickOnce e dovranno elevare il set di autorizzazioni per l'applicazione a attendibilità totale.  
  
 Inoltre, le applicazioni XBAPs non possono visualizzare finestre o finestre di dialogo per impostazione predefinita. Per una discussione sulle considerazioni sulla sicurezza delle applicazioni autonome, vedere strategia di sicurezza di [WPF-sicurezza della piattaforma](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Altri tipi di finestre  
 <xref:System.Windows.Navigation.NavigationWindow> è una finestra progettata per ospitare contenuto navigabile. Per ulteriori informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 Le finestre di dialogo sono finestre usate spesso per raccogliere informazioni da un utente in modo da completare una funzione. Ad esempio, quando un utente desidera aprire un file, la finestra di dialogo **Apri file** viene in genere visualizzata da un'applicazione per ottenere il nome del file dall'utente. Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Panoramica sulle finestre di dialogo](dialog-boxes-overview.md)
- [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)
