---
title: Ospitare contenuto WPF in Win32
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: ff95b330ff67e916a4d27ef841e757998d847c8b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735314"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Procedura dettagliata: hosting di contenuto WPF in Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale nel codice Win32, potrebbe essere più efficace aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità all'applicazione anziché riscrivere il codice originale. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un meccanismo semplice per l'hosting di contenuto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra di Win32.  
  
 In questa esercitazione viene descritto come scrivere un'applicazione di esempio, [ospitando contenuto WPF in un esempio di finestra Win32](https://go.microsoft.com/fwlink/?LinkID=160004), che ospita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in una finestra Win32. È possibile estendere questo esempio per ospitare qualsiasi finestra di Win32. Poiché comporta la combinazione di codice gestito e non gestito, l'applicazione viene scritta in C++/cli.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti  
 Questa esercitazione presuppone una conoscenza di base della programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Win32. Per un'introduzione di base alla programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Introduzione](../getting-started/index.md). Per un'introduzione alla programmazione Win32, è necessario fare riferimento a uno dei numerosi libri sull'argomento, in particolare *programmare Windows* di Charles Petzold.  
  
 Poiché l'esempio che accompagna questa esercitazione è implementato in/CLI C++, in questa esercitazione si presuppone una certa familiarità con C++ l'uso di per programmare l'API Windows, oltre a comprendere la programmazione del codice gestito. La familiarità C++con/CLI è utile ma non essenziale.  
  
> [!NOTE]
> Questa esercitazione include numerosi esempi di codice relativi all'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. Per il codice di esempio completo, vedere l'esempio relativo all' [hosting di contenuto WPF in una finestra Win32](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedura di base  
 In questa sezione viene illustrata la procedura di base utilizzata per ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in una finestra Win32. Le sezioni rimanenti illustrano in dettaglio i vari passaggi.  
  
 La chiave per ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in una finestra Win32 è la classe <xref:System.Windows.Interop.HwndSource>. Questa classe esegue il wrapping del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra Win32, consentendo di incorporarlo nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio. L'approccio seguente combina Win32 e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un'unica applicazione.  
  
1. Implementare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come classe gestita.  
  
2. Implementare un'applicazione Windows con C++/cli. Se si inizia con un'applicazione esistente e il C++ codice non gestito, in genere è possibile abilitarlo per chiamare il codice gestito modificando le impostazioni del progetto in modo da includere il flag del compilatore `/clr`.  
  
3. Impostare il modello di threading su apartment a thread singolo (STA).  
  
4. Gestire la notifica [WM_CREATE](/windows/desktop/winmsg/wm-create)nella procedura della finestra ed eseguire le operazioni seguenti:  
  
    1. Creare un nuovo oggetto <xref:System.Windows.Interop.HwndSource> con la finestra padre come parametro `parent`.  
  
    2. Creare un'istanza della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Assegnare un riferimento all'oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto alla proprietà <xref:System.Windows.Interop.HwndSource.RootVisual%2A> dell'<xref:System.Windows.Interop.HwndSource>.  
  
    4. Ottenere HWND per il contenuto. La proprietà <xref:System.Windows.Interop.HwndSource.Handle%2A> dell'oggetto <xref:System.Windows.Interop.HwndSource> contiene l'handle di finestra (HWND). Per ottenere un HWND utilizzabile nella parte non gestita dell'applicazione, eseguire il cast di `Handle.ToPointer()` a un HWND.  
  
5. Implementare una classe gestita contenente un campo statico con un riferimento al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa classe consente di ottenere un riferimento al contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dal codice Win32.  
  
6. Assegnare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al campo statico.  
  
7. Ricevere notifiche dal contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] connettendo un gestore a uno o più eventi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Comunicare con il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usando il riferimento archiviato nel campo statico per impostare le proprietà ed eseguire altre operazioni.  
  
> [!NOTE]
> È anche possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per implementare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Tuttavia, sarà necessario compilarlo separatamente come libreria a collegamento dinamico (DLL) e fare riferimento a tale DLL dall'applicazione Win32. La parte restante della procedura è simile a quella appena descritta.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementazione dell'applicazione host
 In questa sezione viene descritto come ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in un'applicazione Win32 di base. Il contenuto stesso viene implementato in C++/CLI come classe gestita. In gran parte si tratta di semplice programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Gli aspetti principali dell'implementazione del contenuto vengono illustrati in [implementazione del contenuto WPF](#implementing_the_wpf_page).

- [Applicazione di base](#the_basic_application)

- [Hosting del contenuto WPF](#hosting_the_wpf_page)

- [Riferimento al contenuto WPF](#holding_a_reference)

- [Comunicazione con il contenuto WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Applicazione di base
 Il punto di partenza per l'applicazione host consiste nel creare un modello di Visual Studio 2005.

1. Aprire Visual Studio 2005 e scegliere **nuovo progetto** dal menu **file** .

2. Selezionare **Win32** dall'elenco dei tipi di C++ progetto visivi. Se il linguaggio predefinito non C++è, questi tipi di progetto sono disponibili in **altri linguaggi**.

3. Selezionare un modello di **progetto Win32** , assegnare un nome al progetto e fare clic su **OK** per avviare la **creazione guidata applicazione Win32**.

4. Accettare le impostazioni predefinite della procedura guidata e fare clic su **fine** per avviare il progetto.

 Il modello crea un'applicazione Win32 di base, tra cui:

- Un punto di ingresso per l'applicazione.

- Una finestra, con una procedura di finestra associata (WndProc).

- Menu con intestazioni di **file** e della **Guida** . Il menu **file** contiene un elemento **Exit** che chiude l'applicazione. Il menu? contiene un elemento about che **consente** di avviare una semplice finestra **di** dialogo.

 Prima di iniziare a scrivere il codice per ospitare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario apportare due modifiche al modello di base.

 La prima consiste nel compilare il progetto come codice gestito. Per impostazione predefinita, il progetto viene compilato come codice non gestito. Tuttavia, dal momento che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è implementato in codice gestito, il progetto deve essere compilato di conseguenza.

1. Fare clic con il pulsante destro del mouse sul nome del progetto in **Esplora soluzioni** e scegliere **Proprietà** dal menu di scelta rapida per aprire la finestra di dialogo **pagine delle proprietà** .

2. Selezionare **proprietà di configurazione** nella visualizzazione albero nel riquadro sinistro.

3. Selezionare supporto **Common Language Runtime** dall'elenco **impostazioni predefinite progetto** nel riquadro di destra.

4. Selezionare **supporto Common Language Runtime (/CLR)** dall'elenco a discesa.

> [!NOTE]
> Questo flag del compilatore consente di usare codice gestito nell'applicazione, ma il codice non gestito verrà comunque compilato come in precedenza.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa il modello di threading STA (apartment a thread singolo). Per funzionare correttamente con il codice del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario impostare il modello di threading dell'applicazione su STA applicando un attributo al punto di ingresso.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hosting del contenuto WPF
 Il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è una semplice applicazione di immissione dell'indirizzo. È costituito da diversi controlli <xref:System.Windows.Controls.TextBox> nei quali immettere nome utente, indirizzo e così via. Sono inoltre disponibili due <xref:System.Windows.Controls.Button> controlli, **OK** e **Annulla**. Quando l'utente fa clic su **OK**, il gestore dell'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del pulsante raccoglie i dati dai controlli <xref:System.Windows.Controls.TextBox>, li assegna alle proprietà corrispondenti e genera un evento personalizzato, `OnButtonClicked`. Quando l'utente fa clic su **Annulla**, il gestore genera semplicemente `OnButtonClicked`. L'oggetto argomento dell'evento per `OnButtonClicked` contiene un campo booleano che indica il pulsante scelto.

 Il codice per ospitare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene implementato in un gestore per la notifica [WM_CREATE](/windows/desktop/winmsg/wm-create) nella finestra host.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Il metodo `GetHwnd` acquisisce informazioni sulle dimensioni e sulla posizione più l'handle della finestra padre e restituisce l'handle della finestra del contenuto della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitata.

> [!NOTE]
> Non è possibile usare una direttiva `#using` per lo spazio dei nomi `System::Windows::Interop`, in quanto si creerebbe un conflitto di nomi tra la struttura <xref:System.Windows.Interop.MSG> nello spazio dei nomi e la struttura MSG dichiarata in winuser.h. Al contrario, occorre usare nomi completi per accedere al contenuto dello spazio dei nomi.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Non è possibile ospitare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] direttamente nella finestra dell'applicazione. Al contrario, occorre prima creare un oggetto <xref:System.Windows.Interop.HwndSource> per eseguire il wrapping del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questo oggetto è fondamentalmente una finestra progettata per ospitare un contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per ospitare l'oggetto <xref:System.Windows.Interop.HwndSource> nella finestra padre, è necessario crearlo come elemento figlio di una finestra Win32 che fa parte dell'applicazione. I parametri del costruttore <xref:System.Windows.Interop.HwndSource> contengono molto le stesse informazioni che verrebbero passate a CreateWindow quando si crea una finestra figlio Win32.

 Si crea quindi un'istanza del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto contenuto. In questo caso, il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene implementato come classe separata, `WPFPage`, usando C++/cli. È anche possibile implementare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. A tale scopo, tuttavia, è necessario configurare un progetto separato e compilare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come una DLL. È possibile aggiungere al progetto un riferimento a tale DLL e utilizzare tale riferimento per creare un'istanza del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Per visualizzare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella finestra figlio, assegnare un riferimento al contenuto della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alla proprietà <xref:System.Windows.Interop.HwndSource.RootVisual%2A> della <xref:System.Windows.Interop.HwndSource>.

 La riga di codice successiva associa un gestore eventi, `WPFButtonClicked`, all'evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del contenuto `OnButtonClicked`. Questo gestore viene chiamato quando l'utente fa clic sul pulsante **OK** o **Annulla** . Per ulteriori informazioni su questo gestore eventi, vedere [communicating_with_the_WPF contenuto](#communicating_with_the_page) .

 La riga finale del codice illustrata restituisce l'handle della finestra (HWND) associato all'oggetto <xref:System.Windows.Interop.HwndSource>. È possibile usare questo handle dal codice Win32 per inviare messaggi alla finestra ospitata, sebbene l'esempio non lo faccia. L'oggetto <xref:System.Windows.Interop.HwndSource> genera un evento ogni volta che riceve un messaggio. Per elaborare i messaggi, chiamare il metodo <xref:System.Windows.Interop.HwndSource.AddHook%2A> per associare un gestore di messaggi, quindi elaborare i messaggi in tale gestore.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Riferimento al contenuto WPF
 Per molte applicazioni si vorrà comunicare con il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un secondo momento. Ad esempio, sarà possibile modificare le proprietà del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] o fare in modo che l'oggetto <xref:System.Windows.Interop.HwndSource> ospiti un contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diverso. A tale scopo, è necessario un riferimento all'oggetto <xref:System.Windows.Interop.HwndSource> o al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'oggetto <xref:System.Windows.Interop.HwndSource> e il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associato restano in memoria fino all'eliminazione dell'handle della finestra. Tuttavia, la variabile assegnata all'oggetto <xref:System.Windows.Interop.HwndSource> uscirà dall'ambito non appena si esce dalla procedura di finestra. Il modo personalizzato per gestire questo problema con le applicazioni Win32 consiste nell'usare una variabile statica o globale. Sfortunatamente, non è possibile assegnare un oggetto gestito ai suddetti tipi di variabili. È possibile assegnare l'handle della finestra associato all'oggetto <xref:System.Windows.Interop.HwndSource> a una variabile globale o statica, ma ciò non consentirà di accedere all'oggetto in questione.

 La soluzione più semplice a questo problema consiste nell'implementare una classe gestita contenente un insieme di campi statici che a loro volta contengono i riferimenti agli oggetti gestiti ai quali si vuole accedere. Nell'esempio viene usata la classe `WPFPageHost`, che contiene un riferimento al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oltre ai valori iniziali di diverse proprietà, modificabili in un secondo momento dall'utente. La classe viene definita nell'intestazione.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 La seconda parte della funzione `GetHwnd` assegna valori ai suddetti campi che verranno usati in un secondo momento, con `myPage` ancora nell'ambito.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Comunicazione con il contenuto WPF
 Esistono due tipi di comunicazione con il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'applicazione riceve informazioni dal contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] quando l'utente fa clic sui pulsanti **OK** o **Annulla** . L'applicazione dispone anche di un'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] che consente di modificare diverse proprietà del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ad esempio il colore di sfondo o le dimensioni predefinite del carattere.

 Come indicato in precedenza, quando l'utente fa clic su uno dei pulsanti il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un evento `OnButtonClicked`. L'applicazione associa un gestore a questo evento per ricevere le notifiche. Se è stato fatto clic sul pulsante **OK** , il gestore ottiene le informazioni sull'utente dal contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e le Visualizza in un set di controlli statici.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Il gestore riceve un oggetto argomento dell'evento personalizzato dal contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], `MyPageEventArgs`. La proprietà `IsOK` dell'oggetto è impostata su `true` se è stato fatto clic sul pulsante **OK** e `false` se è stato fatto clic sul pulsante **Annulla** .

 Se è stato fatto clic sul pulsante **OK** , il gestore ottiene un riferimento al contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dalla classe contenitore. Raccoglie quindi le informazioni utente contenute nelle proprietà del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associate e sa i controlli statici per visualizzare le informazioni nella finestra padre. Poiché i dati del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono sotto forma di stringa gestita, è necessario eseguirne il marshalling per l'uso da parte di un controllo Win32. Se è stato fatto clic sul pulsante **Annulla** , il gestore cancella i dati dai controlli statici.

 L'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione fornisce un set di pulsanti di opzione che consentono di modificare il colore di sfondo del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e diverse proprietà correlate al tipo di carattere. Nell'esempio seguente viene illustrato un estratto della procedura di finestra (WndProc) dell'applicazione, nonché la gestione dei messaggi tramite la quale è possibile impostare varie proprietà in messaggi diversi, incluso il colore di sfondo. La parte restante è simile, pertanto non viene illustrata. Vedere l'esempio completo per i dettagli e il contesto.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Per impostare il colore di sfondo, ottenere un riferimento al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) da `WPFPageHost` e impostare la proprietà del colore di sfondo sul colore appropriato. Nell'esempio vengono usate tre opzioni di colore: il colore originale, verde chiaro o salmone chiaro. Il colore di sfondo originale viene archiviato come campo statico nella classe `WPFPageHost`. Per impostare gli altri due colori, creare un nuovo oggetto <xref:System.Windows.Media.SolidColorBrush> e passare al costruttore un valore di colore statico dall'oggetto <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementazione della pagina WPF
 È possibile ospitare e usare il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] senza alcuna conoscenza dell'implementazione effettiva. Se il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato incluso in una DLL separata, potrebbe essere stato compilato in qualsiasi linguaggio Common Language Runtime (CLR). Di seguito viene riportata una breve procedura C++dettagliata dell'implementazione di/CLI utilizzata nell'esempio. Questa sezione contiene le sottosezioni seguenti.

- [Layout](#page_layout)

- [Restituzione dei dati alla finestra host](#returning_data_to_window)

- [Impostazione delle proprietà WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Layout
 Gli elementi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono costituiti da cinque controlli <xref:System.Windows.Controls.TextBox>, con i controlli di <xref:System.Windows.Controls.Label> associati: Name, Address, City, state e zip. Sono disponibili anche due controlli <xref:System.Windows.Controls.Button>, **OK** e **Annulla**

 Il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è implementato nella classe `WPFPage`. Il layout viene gestito mediante un apposito elemento <xref:System.Windows.Controls.Grid>. La classe eredita da <xref:System.Windows.Controls.Grid>, il che la rende effettivamente l'elemento radice del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Il costruttore del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] accetta la larghezza e l'altezza richieste e ridimensiona il <xref:System.Windows.Controls.Grid> di conseguenza. Viene quindi definito il layout di base creando un set di <xref:System.Windows.Controls.ColumnDefinition> e <xref:System.Windows.Controls.RowDefinition> oggetti e aggiungendoli rispettivamente al <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> di base degli oggetti e alle raccolte di <xref:System.Windows.Controls.Grid.RowDefinitions%2A>. Viene così definita una griglia di cinque righe e sette colonne, le cui dimensioni sono determinate dal contenuto delle celle.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Successivamente il costruttore aggiunge gli elementi dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a <xref:System.Windows.Controls.Grid>. Il primo elemento è il testo del titolo, ovvero un controllo <xref:System.Windows.Controls.Label> centrato nella prima riga della griglia.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 La riga successiva contiene il controllo <xref:System.Windows.Controls.Label> Name e il controllo <xref:System.Windows.Controls.TextBox> associato. Dal momento che per ogni coppia etichetta/casella di testo viene usato lo stesso codice, questo viene collocato in una coppia di metodi privati e usato per tutte e cinque le coppie etichetta/casella di testo. I metodi creano il controllo appropriato e chiamano i metodi <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Controls.Grid.SetColumn%2A> statici della classe <xref:System.Windows.Controls.Grid.SetRow%2A> per posizionare i controlli nella cella appropriata. Una volta creato il controllo, nell'esempio viene chiamato il metodo <xref:System.Windows.Controls.UIElementCollection.Add%2A> sulla proprietà <xref:System.Windows.Controls.Panel.Children%2A> di <xref:System.Windows.Controls.Grid> per aggiungere il controllo alla griglia. Il codice usato per aggiungere le coppie etichetta/casella di testo restanti è simile. Vedere il codice di esempio per i dettagli.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 D seguito viene riportata l'implementazione dei due metodi:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Infine, l'esempio aggiunge i pulsanti **OK** e **Annulla** e connette un gestore eventi ai relativi eventi <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Restituzione dei dati alla finestra host
 Facendo clic su un pulsante, viene generato il rispettivo evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. La finestra host potrebbe semplicemente associare i gestori a questi eventi e ottenere i dati direttamente dai controlli <xref:System.Windows.Controls.TextBox>. Nell'esempio viene usato un approccio meno diretto. Gestisce la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> all'interno del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e quindi genera un `OnButtonClicked`di eventi personalizzato per notificare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ciò consente al contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di eseguire una convalida dei parametri prima di notificare l'host. Il gestore ottiene il testo dai controlli <xref:System.Windows.Controls.TextBox> e lo assegna a proprietà pubbliche, dalle quali l'host può recuperare le informazioni.

 Dichiarazione di evento in WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Gestore eventi <xref:System.Windows.Controls.Primitives.ButtonBase.Click> in WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Impostazione delle proprietà WPF
 L'host Win32 consente all'utente di modificare diverse proprietà del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Dal lato Win32, è sufficiente modificare le proprietà. L'implementazione nella classe del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è leggermente più complessa, poiché non esiste un'unica proprietà globale che controlla i tipi di carattere per tutti i controlli. La proprietà adatta per ogni controllo viene modificata nelle funzioni di accesso dell'insieme di proprietà. Nell'esempio seguente viene illustrato il codice per la proprietà `DefaultFontFamily`. Impostando la proprietà, viene chiamato un metodo privato che a sua volta imposta le proprietà <xref:System.Windows.Controls.Control.FontFamily%2A> per i vari controlli.

 Da WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Da WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
