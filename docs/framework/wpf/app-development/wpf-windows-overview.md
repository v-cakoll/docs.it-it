---
title: Cenni preliminari sulle finestre WPF
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
ms.openlocfilehash: ad7d5225dbaaae544ab463a8f4f16bc43bdf4098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-windows-overview"></a>Cenni preliminari sulle finestre WPF
Gli utenti interagiscono con le applicazioni autonome di Windows Presentation Foundation (WPF) tramite windows. Lo scopo principale di una finestra è ospitare contenuto tramite cui visualizzare dati e permettere agli utenti di interagire con i dati. Autonomo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni forniscono le rispettive finestre utilizzando la <xref:System.Windows.Window> classe. Questo argomento vengono presentate <xref:System.Windows.Window> prima di analizzare le nozioni di base di creazione e gestione di windows in applicazioni autonome.  
  
> [!NOTE]
>  Ospitate da browser [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni, inclusi [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] e cavi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagine, non fornire le rispettive finestre. Invece, sono ospitati nelle finestre fornite da [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]. Vedere [panoramica delle applicazioni Browser XAML di WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
  
<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Classe Window  
 La figura seguente mostra le parti che costituiscono una finestra.  
  
 ![Elementi di una finestra](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Un finestra è suddivisa in due aree: l'area non client e l'area client.  
  
 Il *area non client* di una finestra viene implementata da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e include le parti di una finestra che sono comuni alla maggior parte delle finestre, inclusi i seguenti:  
  
-   Un bordo.  
  
-   Una barra del titolo.  
  
-   Un'icona.  
  
-   Pulsanti Riduci a icona, Ingrandisci e Ripristina.  
  
-   Un pulsante Chiudi.  
  
-   Un menu di sistema con voci di menu che permettono agli utenti di ridurre al minimo, ingrandire, ripristinare, spostare, ridimensionare e chiudere una finestra.  
  
 Il *area client* di una finestra è l'area all'interno dell'area non client e viene utilizzato dagli sviluppatori per aggiungere contenuto specifico dell'applicazione, ad esempio le barre dei menu, barre degli strumenti e controlli.  
  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], una finestra viene incapsulata dalle classi di <xref:System.Windows.Window> classe che consente di eseguire le operazioni seguenti:  
  
-   Visualizzare una finestra.  
  
-   Configurare dimensioni, posizione e aspetto di una finestra.  
  
-   Ospitare contenuto specifico dell'applicazione.  
  
-   Gestire la durata di una finestra.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementazione di una finestra  
 L'implementazione di una finestra tipico include aspetto e comportamento, in cui *aspetto* definisce l'aspetto di una finestra a utenti e *comportamento* definisce il modo in cui le funzioni di una finestra quando gli utenti interagiscono con esso. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], è possibile implementare l'aspetto e comportamento di una finestra tramite codice o [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 In generale, tuttavia, l'aspetto di una finestra viene implementato utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e il relativo comportamento viene implementato tramite code-behind, come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Per abilitare un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di markup e il file code-behind per essere utilizzati insieme, sono necessari i seguenti:  
  
-   Nel markup di `Window` elemento deve includere il `x:Class` attributo. Quando l'applicazione viene compilata, l'esistenza di `x:Class` nel markup file fa sì che [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] per creare un `partial` classe che deriva da <xref:System.Windows.Window> e ha il nome specificato per il `x:Class` attributo. Questa operazione richiede l'aggiunta di un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dichiarazione dello spazio dei nomi per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Generato `partial` classe implementa il `InitializeComponent` metodo, che viene chiamata per registrare gli eventi e impostare le proprietà implementate nel markup.  
  
-   Nel code-behind, la classe deve essere un `partial` classe con lo stesso nome specificato per il `x:Class` deve derivare l'attributo nel markup e da <xref:System.Windows.Window>. In questo modo il file code-behind può essere associato il `partial` classe generata per il file di markup quando l'applicazione viene compilata (vedere [compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   Nel code-behind, il <xref:System.Windows.Window> classe deve implementare un costruttore che chiama il `InitializeComponent` metodo. `InitializeComponent` viene implementato per il markup generata per il file `partial` classe per registrare gli eventi e impostare le proprietà che sono definite nel markup.  
  
> [!NOTE]
>  Quando si aggiunge un nuovo <xref:System.Windows.Window> al progetto utilizzando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Window> viene implementata utilizzando sia markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind come descritte di seguito.  
  
 Con questa configurazione, è possibile concentrarsi sulla definizione dell'aspetto della finestra di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e sull'implementazione del comportamento nel code-behind. Nell'esempio seguente viene illustrata una finestra con un pulsante, implementato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e un gestore eventi per il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, implementata nel code-behind.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Configurazione di una definizione di finestra per MSBuild  
 Modalità di implementazione di finestra determina come viene configurato per [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. Per una finestra che viene definita con entrambi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup e code-behind:  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i file di markup sono configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementi.  
  
-   File code-behind sono configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` elementi.  
  
 Come illustrato nell'esempio seguente [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] file di progetto.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Per informazioni sulla compilazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni, vedere [compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Durata di una finestra  
 Come con qualsiasi classe, una finestra ha una durata che inizia alla creazione della prima istanza, dopo la quale viene aperta, attivata e disattivata e infine chiusa.  
  
  
<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Apertura di una finestra  
 Per aprire una finestra, è necessario prima di tutto crearne un'istanza, come mostrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In questo esempio, il `MarkupAndCodeBehindWindow` viene creata un'istanza all'avvio dell'applicazione, che si verifica quando il <xref:System.Windows.Application.Startup> viene generato l'evento.  
  
 Quando viene creata un'istanza di una finestra, un riferimento a esso viene automaticamente aggiunto a un elenco di windows che è gestito dal <xref:System.Windows.Application> oggetto (vedere <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Inoltre, la prima finestra deve essere creata un'istanza è, per impostazione predefinita, impostata da <xref:System.Windows.Application> come finestra principale dell'applicazione (vedere <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 Infine, la finestra viene aperta chiamando il <xref:System.Windows.Window.Show%2A> metodo; il risultato è illustrato nella figura seguente.  
  
 ![Finestra aperta mediante la chiamata di Window.Show](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Una finestra che viene aperto chiamando <xref:System.Windows.Window.Show%2A> è una finestra non modale, che significa che l'applicazione funziona in modalità che consente agli utenti di attivare altre finestre dell'applicazione stessa.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> viene chiamata per aprire windows, ad esempio le finestre di dialogo modali. Vedere [Panoramica di finestre di dialogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) per ulteriori informazioni.  
  
 Quando <xref:System.Windows.Window.Show%2A> viene chiamato, una finestra esegue operazioni di inizializzazione prima che venga visualizzato per stabilire l'infrastruttura che consente di ricevere l'input dell'utente. Quando la finestra viene inizializzata, il <xref:System.Windows.Window.SourceInitialized> evento viene generato e viene visualizzata la finestra.  
  
 In alternativa, <xref:System.Windows.Application.StartupUri%2A> può essere impostato su specificare la prima finestra che viene aperto automaticamente all'avvio dell'applicazione.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 All'avvio dell'applicazione, la finestra specificata dal valore di <xref:System.Windows.Application.StartupUri%2A> viene aperto in maniera non modale; internamente, la finestra viene aperta chiamando il relativo <xref:System.Windows.Window.Show%2A> (metodo).  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Proprietà della finestra  
 Una finestra che viene aperto con il <xref:System.Windows.Window.Show%2A> (metodo) non dispone di una relazione implicita con la finestra che lo ha creato, è possibile interagire con entrambe le finestre indipendente, il che significa che entrambe le finestre possono eseguire le operazioni seguenti:  
  
-   Coprire l'altra (a meno che non dispone di una delle finestre relative <xref:System.Windows.Window.Topmost%2A> proprietà impostata su `true`).  
  
-   Essere ridotte a icona, ingrandite e ripristinate senza influire sull'altra.  
  
 Alcune finestre richiedono una relazione con la finestra da cui vengono aperte. Ad esempio, un [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] applicazione vengano aperte finestre delle proprietà e il cui comportamento tipico è la copertura della finestra in cui vengono create le finestre degli strumenti. Queste finestre devono inoltre essere chiuse, ridotte a icona, ingrandite e ripristinate insieme alla finestra da cui sono state create. È possibile stabilire questa relazione apportando un'unica finestra *proprio* un'altra e impostando il <xref:System.Windows.Window.Owner%2A> proprietà del *proprietà finestra* con un riferimento al *proprietario finestra*. come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Dopo aver stabilito la proprietà:  
  
-   La finestra di proprietà può fare riferimento alla finestra proprietaria controllando il valore della relativa <xref:System.Windows.Window.Owner%2A> proprietà.  
  
-   La finestra proprietaria può individuare tutte le finestre possiede controllando il valore della relativa <xref:System.Windows.Window.OwnedWindows%2A> proprietà.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Impedire l'attivazione delle finestre  
 Esistono scenari in cui windows non devono essere attivate quando viene visualizzata, ad esempio conversazione di un'applicazione di tipo messenger Internet o di un'applicazione di posta elettronica di notifica windows.  
  
 Se l'applicazione dispone di una finestra che non deve essere attivata quando visualizzata, è possibile impostare il relativo <xref:System.Windows.Window.ShowActivated%2A> proprietà `false` prima di chiamare il <xref:System.Windows.Window.Show%2A> metodo per la prima volta. Di conseguenza:  
  
-   La finestra non viene attivata.  
  
-   La finestra <xref:System.Windows.Window.Activated> non viene generato l'evento.  
  
-   La finestra attualmente attivata resta attivata.  
  
 La finestra viene attivata, tuttavia, non appena l'utente fa clic sull'area client o non client. In questo caso:  
  
-   La finestra viene attivata.  
  
-   La finestra <xref:System.Windows.Window.Activated> viene generato l'evento.  
  
-   La finestra precedentemente attivata viene disattivata.  
  
-   La finestra <xref:System.Windows.Window.Deactivated> e <xref:System.Windows.Window.Activated> gli eventi vengono generati in seguito come previsto in risposta alle azioni dell'utente.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Attivazione di finestre  
 Alla prima apertura di una finestra, diventa la finestra attiva (a meno che non sia visualizzata con <xref:System.Windows.Window.ShowActivated%2A> impostato su `false`). Il *finestra attiva* è la finestra che sta correntemente ricevendo l'input dell'utente, ad esempio pressioni di tasti e i clic del mouse. Quando una finestra diventa attiva, viene generato il <xref:System.Windows.Window.Activated> evento.  
  
> [!NOTE]
>  Prima apertura di una finestra, il <xref:System.Windows.FrameworkElement.Loaded> e <xref:System.Windows.Window.ContentRendered> gli eventi vengono generati solo dopo che il <xref:System.Windows.Window.Activated> viene generato l'evento. A tal fine, una finestra può considerarsi effettivamente aperto quando <xref:System.Windows.Window.ContentRendered> viene generato.  
  
 Dopo l'attivazione di una finestra, un utente può attivare un'altra finestra nella stessa applicazione oppure attivare un'altra applicazione. In questo caso, la finestra attualmente attiva viene disattivata e genera il <xref:System.Windows.Window.Deactivated> evento. Analogamente, quando l'utente seleziona una finestra attualmente disattivata, la finestra diventa nuovamente attiva e <xref:System.Windows.Window.Activated> viene generato.  
  
 Un motivo comune per gestire <xref:System.Windows.Window.Activated> e <xref:System.Windows.Window.Deactivated> consiste nell'abilitare e disabilitare la funzionalità che può essere eseguito solo quando è attiva una finestra. Ad esempio, alcune finestre mostrano contenuto interattivo che richiede un input utente o un'attenzione costante, tra cui giochi e lettori video. L'esempio seguente è un lettore video semplificato che illustra come gestire <xref:System.Windows.Window.Activated> e <xref:System.Windows.Window.Deactivated> per implementare questo comportamento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Altri tipi di applicazioni possono comunque eseguire codice in background quando una finestra è disattivata. Ad esempio, un client di posta elettronica può continuare a eseguire il polling del server di posta elettronica mentre l'utente usa altre applicazioni. Applicazioni come queste forniscono un comportamento diverso o aggiuntivo mentre la finestra principale è disattivata. Riguardo al programma di posta elettronica, questo significa aggiungere il nuovo elemento di posta elettronica nella posta in arrivo e aggiungere un'icona di notifica sulla barra delle applicazioni. Un'icona di notifica deve essere visualizzata solo quando la finestra di posta elettronica non è attivo e che può essere determinata controllando la <xref:System.Windows.Window.IsActive%2A> proprietà.  
  
 Se un'attività in background viene completata, è consigliabile una finestra notificare all'utente più tempestivo chiamando <xref:System.Windows.Window.Activate%2A> metodo. Se l'utente interagisce con un'altra applicazione attivata quando <xref:System.Windows.Window.Activate%2A> viene chiamato, fa lampeggiare il pulsante della finestra della barra delle applicazioni. Se un utente interagisce con l'applicazione corrente, la chiamata <xref:System.Windows.Window.Activate%2A> fornirà la finestra di primo piano.  
  
> [!NOTE]
>  È possibile gestire l'attivazione con ambito di applicazione utilizzando il <xref:System.Windows.Application.Activated?displayProperty=nameWithType> e <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> eventi.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Chiusura di una finestra  
 La durata di una finestra si avvicina alla fine quando la finestra viene chiusa da un utente. Una finestra può essere chiusa tramite elementi nell'area non client, tra cui i seguenti:  
  
-   Il **Chiudi** elemento del **sistema** menu.  
  
-   ALT + F4.  
  
-   Premendo il **Chiudi** pulsante.  
  
 È possibile fornire un meccanismo aggiuntivo all'area client per chiudere una finestra, i più comuni dei quali includono:  
  
-   Un **uscita** elemento il **File** menu, in genere nelle finestre dell'applicazione principale.  
  
-   Oggetto **Chiudi** elemento il **File** menu, in genere in una finestra dell'applicazione secondaria.  
  
-   Oggetto **Annulla** pulsante, in genere in una finestra di dialogo modale.  
  
-   Oggetto **Chiudi** pulsante, in genere in una finestra di dialogo non modale.  
  
 Per chiudere una finestra in risposta a uno di questi meccanismi personalizzati, è necessario chiamare il <xref:System.Windows.Window.Close%2A> metodo. Nell'esempio seguente viene implementata la possibilità di chiudere una finestra scegliendo il **uscita** sul **File** menu.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Quando si chiude una finestra, genera due eventi: <xref:System.Windows.Window.Closing> e <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> viene generato prima che la finestra viene chiusa e fornisce un meccanismo mediante il quale è possibile evitare la chiusura. Un motivo comune per cui impedire la chiusura di una finestra è se la finestra contiene dati modificati. In questo caso, il <xref:System.Windows.Window.Closing> evento può essere gestito per determinare se i dati siano stati modificati e, in tal caso, chiedere all'utente se proseguire la chiusura della finestra senza salvare i dati o annullare la chiusura della finestra. L'esempio seguente illustra gli aspetti chiavi della gestione <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  
 
  
 Il <xref:System.Windows.Window.Closing> gestore eventi viene passato un <xref:System.ComponentModel.CancelEventArgs>, che implementa il `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà che è impostata su `true` per impedire la chiusura di una finestra.  
  
 Se <xref:System.Windows.Window.Closing> non viene gestita, o viene gestito ma non è stato annullato, la finestra verrà chiusa. Prima di una finestra viene effettivamente chiusa, <xref:System.Windows.Window.Closed> viene generato. A questo punto, non è più possibile impedire la chiusura di una finestra.  
  
> [!NOTE]
>  Un'applicazione può essere configurata per arrestare automaticamente alla chiusura di finestra principale dell'applicazione (vedere <xref:System.Windows.Application.MainWindow%2A>) o l'ultima finestra viene chiusa. Per informazioni dettagliate, vedere <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Una finestra può essere chiusa in modo esplicito tramite i meccanismi forniti nelle aree non client e client, anche una finestra può essere chiuso in modo implicito come risultato di comportamento in altre parti dell'applicazione o [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], inclusi i seguenti:  
  
-   Un utente si disconnette o arresta il sistema.  
  
-   Chiude il proprietario di una finestra (vedere <xref:System.Windows.Window.Owner%2A>).  
  
-   La finestra principale dell'applicazione viene chiusa e <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
-   Chiamata del metodo <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
>  Una volta chiusa, una finestra non può più essere riaperta.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Eventi di durata di una finestra  
 La figura seguente mostra la sequenza degli eventi principali per la durata di una finestra.  
  
 ![Durata di una finestra](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 Nella figura seguente viene illustrata la sequenza degli eventi principali nella durata di una finestra che viene visualizzata senza l'attivazione (<xref:System.Windows.Window.ShowActivated%2A> è impostato su `false` prima di visualizzare la finestra).  
  
 ![Durata di una finestra &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Posizione della finestra  
 Mentre è aperta, una finestra ha una posizione nelle dimensioni x e y relative al desktop. Questo percorso può essere determinato controllando il <xref:System.Windows.Window.Left%2A> e <xref:System.Windows.Window.Top%2A> proprietà, rispettivamente. È possibile impostare queste proprietà in modo da modificare la posizione della finestra.  
  
 È inoltre possibile specificare la posizione iniziale di un <xref:System.Windows.Window> quando viene innanzitutto visualizzato impostando il <xref:System.Windows.Window.WindowStartupLocation%2A> proprietà con uno dei seguenti <xref:System.Windows.WindowStartupLocation> valori di enumerazione:  
  
-   <xref:System.Windows.WindowStartupLocation.CenterOwner> (impostazione predefinita)  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Se la posizione di avvio è specificata come <xref:System.Windows.WindowStartupLocation.Manual>e il <xref:System.Windows.Window.Left%2A> e <xref:System.Windows.Window.Top%2A> non sono state impostate le proprietà, <xref:System.Windows.Window> chiederà Windows per un percorso siano visibili nel.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Finestre in primo piano e ordine z  
 Oltre ad avere una posizione nelle dimensioni x e y, una finestra ha anche una dimensione z, che ne determina la posizione verticale rispetto alle altre finestre. Questo concetto è noto con il nome di ordine z della finestra e ne esistono due tipi: ordine z normale e ordine z in primo piano. Il percorso di una finestra nel *ordine z normale* varia a seconda che sia attualmente attivo o meno. Per impostazione predefinita, una finestra è posizionata in base all'ordine z normale. Il percorso di una finestra nel *in primo piano nell'ordine z* anche dipende dal fatto è attualmente attiva o non. Inoltre, le finestre posizionate in base all'ordine z in primo piano si trovano sempre al di sopra di quelle posizionate in base all'ordine z normale. Una finestra si trova nell'ordine z di primo piano impostando il relativo <xref:System.Windows.Window.Topmost%2A> proprietà `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 In entrambi gli ordini z la finestra attualmente attiva viene visualizzata al di sopra delle altre finestre in base allo stesso ordine z.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Dimensioni finestra  
 Oltre a offrire una posizione nel desktop, una finestra dispone di una dimensione è determinata da diverse proprietà, incluse le varie proprietà di larghezza e altezza e <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, e <xref:System.Windows.FrameworkElement.MaxWidth%2A> consentono di gestire l'intervallo di larghezza di una finestra può avere durante la sua durata e vengono configurati come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Altezza della finestra è gestito da <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, e <xref:System.Windows.FrameworkElement.MaxHeight%2A>e vengono configurati come illustrato nell'esempio seguente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Poiché i diversi valori di larghezza e di altezza specificano ciascuno un intervallo, la larghezza e l'altezza di una finestra ridimensionabile possono corrispondere a qualsiasi valore all'interno dell'intervallo specificato per la rispettiva dimensione. Per rilevare la larghezza corrente e l'altezza, controllare <xref:System.Windows.FrameworkElement.ActualWidth%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A>, rispettivamente.  
  
 Se si desidera la larghezza e altezza della finestra per disporre di una dimensione che si adatta alle dimensioni della finestra del contenuto, è possibile utilizzare il <xref:System.Windows.Window.SizeToContent%2A> proprietà, che presenta i seguenti valori:  
  
-   <xref:System.Windows.SizeToContent.Manual>. Nessun effetto (impostazione predefinita).  
  
-   <xref:System.Windows.SizeToContent.Width>. Adatta alla larghezza del contenuto, che ha lo stesso effetto dell'impostazione sia <xref:System.Windows.FrameworkElement.MinWidth%2A> e <xref:System.Windows.FrameworkElement.MaxWidth%2A> la larghezza del contenuto.  
  
-   <xref:System.Windows.SizeToContent.Height>. Adatta all'altezza del contenuto, che ha lo stesso effetto dell'impostazione sia <xref:System.Windows.FrameworkElement.MinHeight%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> l'altezza del contenuto.  
  
-   <xref:System.Windows.SizeToContent.WidthAndHeight>. Adatta in larghezza e altezza, che ha lo stesso effetto dell'impostazione sia <xref:System.Windows.FrameworkElement.MinHeight%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> l'altezza del contenuto e impostazione entrambi <xref:System.Windows.FrameworkElement.MinWidth%2A> e <xref:System.Windows.FrameworkElement.MaxWidth%2A> la larghezza del contenuto.  
  
 L'esempio seguente mostra una finestra che si ridimensiona automaticamente in base al contenuto, sia in verticale sia in orizzontale, quando viene visualizzata per la prima volta.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Window.SizeToContent%2A> proprietà nel codice per specificare come una finestra viene ridimensionata per adattarsi al contenuto.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Ordine di precedenza per le proprietà di ridimensionamento  
 Essenzialmente, le diverse proprietà per le dimensioni di una finestra si combinano per definire gli intervalli di larghezza e altezza per una finestra ridimensionabile. Per garantire un intervallo valido è mantenuto, <xref:System.Windows.Window> valuta i valori delle proprietà della dimensione utilizzando i seguenti ordini di precedenza.  
  
 **Per le proprietà di altezza:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Per le proprietà di larghezza:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 L'ordine di precedenza possibile inoltre determinare le dimensioni di una finestra quando viene ingrandito, che viene gestita la <xref:System.Windows.Window.WindowState%2A> proprietà.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Stato della finestra  
 Per la sua durata, una finestra ridimensionabile può avere tre stati: normale, ridotta a icona e ingrandita. Una finestra con un *normale* stato rappresenta lo stato predefinito di una finestra. Una finestra con questo stato permette a un utente di spostarla e ridimensionarla usando un controllo di ridimensionamento o il bordo, se è ridimensionabile.  
  
 Una finestra con un *ridotta a icona* stato comprime il pulsante della barra se <xref:System.Windows.Window.ShowInTaskbar%2A> è impostato su `true`; in caso contrario, viene compressa nella dimensione minima può essere e collocata nell'angolo inferiore sinistro del desktop. Nessuno dei due tipi di finestra ridotta a icona può essere ridimensionato tramite un bordo o un controllo di ridimensionamento, anche se una finestra ridotta a icona non visualizzata sulla barra delle applicazioni può essere trascinata sul desktop.  
  
 Una finestra con un *ingrandita* stato si espande per la dimensione massima possibile, sarà solo fino a relativo <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, e <xref:System.Windows.Window.SizeToContent%2A> stabiliscono le proprietà. Come per una finestra ridotta a icona, una finestra ingrandita non può essere ridimensionata tramite un controllo di ridimensionamento o trascinandone il bordo.  
  
> [!NOTE]
>  I valori del <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di una finestra rappresentano sempre i valori per lo stato normale, anche quando la finestra è ingrandita o ridotta a icona.  
  
 Lo stato di una finestra può essere configurato impostando il relativo <xref:System.Windows.Window.WindowState%2A> proprietà, che può avere uno dei seguenti <xref:System.Windows.WindowState> valori di enumerazione:  
  
-   <xref:System.Windows.WindowState.Normal> (impostazione predefinita)  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 L'esempio seguente mostra come creare una finestra visualizzata come ingrandita quando viene aperta.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 In generale, è necessario impostare <xref:System.Windows.Window.WindowState%2A> per configurare lo stato iniziale di una finestra. Quando è visualizzata una finestra ridimensionabile, gli utenti possono premere i pulsanti Riduci a icona, Ingrandisci e Ripristina sulla barra del titolo della finestra per modificarne lo stato.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Aspetto della finestra  
 Per modificare l'aspetto dell'area client di una finestra, è necessario aggiungervi contenuto specifico della finestra, come pulsanti, etichette e caselle di testo. Per configurare l'area non client, <xref:System.Windows.Window> fornisce diverse proprietà, tra cui <xref:System.Windows.Window.Icon%2A> per impostare l'icona di una finestra e <xref:System.Windows.Window.Title%2A> per impostare il titolo.  
  
 È anche possibile modificare l'aspetto e il comportamento del bordo dell'area non client configurando la modalità di ridimensionamento di una finestra, lo stile della finestra e se la finestra verrà o meno visualizzata come pulsante sulla barra delle applicazioni del desktop.  
  
  
<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Modalità di ridimensionamento  
 A seconda di <xref:System.Windows.Window.WindowStyle%2A> proprietà, è possibile controllare come (e se) gli utenti possono ridimensionare la finestra. La scelta dello stile di finestra determina se un utente può ridimensionare la finestra trascinando il bordo con il mouse, se il **Riduci a icona**, **Ingrandisci**, e **ridimensionare** pulsanti Nell'area non client, e, se sono visualizzate, se sono abilitate.  
  
 È possibile configurare la modalità di ridimensionamento di una finestra impostando il relativo <xref:System.Windows.Window.ResizeMode%2A> proprietà, che può essere uno dei seguenti <xref:System.Windows.ResizeMode> valori di enumerazione:  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <xref:System.Windows.ResizeMode.CanResize> (impostazione predefinita)  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Come con <xref:System.Windows.Window.WindowStyle%2A>, la modalità di ridimensionamento di una finestra viene in genere modificata durante la sua durata, il che significa che è molto probabile venga impostata da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Si noti che è possibile rilevare se una finestra ingrandita, ridotta a icona o ripristinata, controllare il <xref:System.Windows.Window.WindowState%2A> proprietà.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Stile della finestra  
 Il bordo esposto dall'area non client di una finestra è adatto per la maggior parte delle applicazioni. In alcuni casi, tuttavia, sono necessari tipi di bordi diversi oppure non è necessario alcun bordo, a seconda del tipo di finestra.  
  
 Per controllare il tipo di bordo di una finestra, impostare il relativo <xref:System.Windows.Window.WindowStyle%2A> proprietà con uno dei seguenti valori del <xref:System.Windows.WindowStyle> enumerazione:  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <xref:System.Windows.WindowStyle.SingleBorderWindow> (impostazione predefinita)  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 L'effetto di questi stili di finestra viene mostrato nella figura seguente.  
  
 ![Stili di finestra](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.PNG "WindowOverviewFigure6")  
  
 È possibile impostare <xref:System.Windows.Window.WindowStyle%2A> utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup o codice; perché è in genere modificata nel corso della durata di una finestra, è molto probabile configurata utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Stile di finestra non rettangolare  
 Esistono inoltre alcune situazioni in cui stili del bordo <xref:System.Windows.Window.WindowStyle%2A> consente di disporre di non sono sufficienti. Ad esempio, si desidera creare un'applicazione con un bordo non rettangolari, ad esempio [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] utilizza.  
  
 Ad esempio, si consideri la finestra a fumetto mostrata nella figura seguente.  
  
 ![Finestra non rettangolare](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Questo tipo di finestra può essere creato tramite l'impostazione di <xref:System.Windows.Window.WindowStyle%2A> proprietà <xref:System.Windows.WindowStyle.None>e utilizzando il supporto speciale che <xref:System.Windows.Window> è per la trasparenza.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Questa combinazione di valori specifica che la finestra deve essere visualizzata come completamente trasparente. In questo stato le aree di controllo (menu Chiudi, pulsanti Riduci a icona, Ingrandisci e Ripristina e così via) dell'area non client della finestra non possono essere usate. Di conseguenza, è necessario fornirne di personalizzate.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Presenza sulla barra delle applicazioni  
 L'aspetto predefinito di una finestra include un pulsante sulla barra delle applicazioni, come quello mostrato nella figura seguente.  
  
 ![Finestra con un pulsante sulla barra delle applicazioni](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.PNG "WindowOverviewFigure7")  
  
 Alcuni tipi di windows non dispongono di un pulsante della barra attività, ad esempio le finestre di dialogo e finestre di messaggio (vedere [Panoramica di finestre di dialogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)). È possibile controllare se il pulsante della barra di una finestra viene visualizzato impostando il <xref:System.Windows.Window.ShowInTaskbar%2A> proprietà (`true` per impostazione predefinita).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Considerazioni sulla sicurezza  
 <xref:System.Windows.Window> richiede `UnmanagedCode` autorizzazione di sicurezza deve essere creata un'istanza. Per le applicazioni installate nel computer locale e da qui avviate, questa è inclusa nel set di autorizzazioni concesse all'applicazione.  
  
 Tuttavia, questo rientra il set di autorizzazioni concesse alle applicazioni vengono avviate dalla locale o Internet intranet zona utilizzando [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]. Di conseguenza, gli utenti riceveranno un [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] avviso di sicurezza e sarà necessario disporre dell'autorizzazione impostata per l'applicazione con attendibilità totale.  
  
 Inoltre, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non è possibile visualizzare le finestre di dialogo o di windows per impostazione predefinita. Per informazioni sulle considerazioni relative alla protezione di applicazione autonoma, vedere [strategia di sicurezza di WPF - sicurezza della piattaforma](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Altri tipi di finestre  
 <xref:System.Windows.Navigation.NavigationWindow> è una finestra che è progettata per ospitare contenuto esplorabile. Per ulteriori informazioni, vedere [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md)).  
  
 Le finestre di dialogo sono finestre usate spesso per raccogliere informazioni da un utente in modo da completare una funzione. Ad esempio, quando un utente sta tentando di aprire un file, il **Apri File** la finestra di dialogo viene visualizzata in genere da un'applicazione per ottenere il nome del file da parte dell'utente. Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Window>  
 <xref:System.Windows.MessageBox>  
 <xref:System.Windows.Navigation.NavigationWindow>  
 <xref:System.Windows.Application>  
 [Panoramica sulle finestre di dialogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)  
 [Compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
