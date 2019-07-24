---
title: Cenni preliminari sugli eventi associati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: a3a2f711840ad7f6e28443dac3c18501cd4400e0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401408"
---
# <a name="attached-events-overview"></a>Cenni preliminari sugli eventi associati
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definisce un componente del linguaggio e un tipo di evento noto come *evento associato*. Il concetto di evento associato consente di aggiungere un gestore per un determinato evento a un elemento arbitrario, anziché a un elemento che definisce o eredita effettivamente l'evento. In questo caso, né l'oggetto che genera potenzialmente l'evento, né l'istanza di gestione di destinazione definisce o possiede in altro modo l'evento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone di aver letto [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md) e [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Sintassi per gli eventi associati  
 Per supportare l'uso degli eventi associati, è necessario che il codice sottostante usi una sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e un modello di codifica specifici di tali eventi.  
  
 Nella sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], l'evento associato non viene specificato solo tramite il nome dell'evento, ma con il tipo proprietario e il nome dell'evento, separati da un punto (.). Dato che il nome di evento è qualificato con il nome del tipo proprietario, la sintassi dell'evento associato consente l'associazione di tale evento a qualsiasi elemento di cui è possibile creare un'istanza.  
  
 Ad esempio, di seguito viene illustrata la sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per collegare un gestore per un evento associato `NeedsCleaning`:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Si noti il prefisso `aqua:`, necessario in questo caso perché l'evento associato è un evento personalizzato tratto da un xmlns mappato personalizzato.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Modalità di implementazione degli eventi associati in WPF  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gli eventi associati sono supportati da un <xref:System.Windows.RoutedEvent> campo e vengono instradati attraverso la struttura ad albero dopo la generazione. In genere, l'origine dell'evento associato (oggetto che genera l'evento) è un'origine di sistema o servizio e l'oggetto che esegue il codice che genera l'evento non è pertanto parte diretta dell'albero degli elementi.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Scenari per gli eventi associati  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gli eventi associati sono presenti in determinate aree di funzionalità in cui è presente un'astrazione a livello di servizio, ad esempio per gli <xref:System.Windows.Input.Mouse> eventi abilitati <xref:System.Windows.Controls.Validation> dalla classe statica o dalla classe. Le classi che interagiscono con il servizio o lo usano possono usano l'evento nella sintassi dell'evento associato o scegliere di usarlo come un evento indirizzato che fa parte del modo in cui la classe integra le funzionalità del servizio.  
  
 Anche se in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono definiti vari eventi associati, gli scenari in cui si usa o si gestisce direttamente l'evento associato sono molto limitati. In genere, l'evento associato serve a scopo di architettura, ma viene quindi inoltrato a un evento indirizzato non associato (supportato con un evento CLR "wrapper").  
  
 Ad esempio <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> , l'evento associato sottostante può essere gestito in modo più semplice in qualsiasi dato <xref:System.Windows.UIElement.MouseDown> <xref:System.Windows.UIElement> usando su <xref:System.Windows.UIElement> , invece di gestire la sintassi degli eventi collegati in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o nel codice. L'evento associato assolve a uno scopo nell'architettura perché consente l'espansione futura dei dispositivi di input. Per simulare l'input del mouse è <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> necessario che il dispositivo ipotetico aumenti solo per simulare l'input del mouse <xref:System.Windows.Input.Mouse> e non è necessario derivare da a questo scopo. Questo scenario comporta tuttavia la gestione di codice degli eventi e la gestione di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dell'evento associato non è attinente a questo scenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Gestione di un evento associato in WPF  
 Il processo di gestione di un evento associato e il codice del gestore che verrà scritto è fondamentalmente lo stesso necessario per un evento indirizzato.  
  
 In genere, un evento associato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non è molto diverso da un evento indirizzato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Le differenze sono date dalla modalità di origine dell'evento e della relativa esposizione da parte di una classe come membro, operazione che ha anche effetto sulla sintassi del gestore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Tuttavia, come indicato in precedenza, gli eventi associati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti non sono destinati in modo particolare alla gestione in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Più spesso, lo scopo dell'evento è quello di consentire la segnalazione di uno stato da parte di un elemento composto a un elemento padre nella composizione, nel qual caso l'evento viene in genere generato nel codice e si basa inoltre sulla gestione della classe nella classe padre rilevante. Ad esempio, gli elementi all' <xref:System.Windows.Controls.Primitives.Selector> interno di un oggetto dovrebbero generare <xref:System.Windows.Controls.Primitives.Selector.Selected> l'evento associato, che è <xref:System.Windows.Controls.Primitives.Selector> quindi una classe gestita dalla classe e quindi potenzialmente convertita dalla <xref:System.Windows.Controls.Primitives.Selector> classe in un evento indirizzato <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> diverso, . Per altre informazioni sugli eventi indirizzati e sulla gestione delle classi, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definizione di eventi associati personalizzati come eventi indirizzati  
 Se si deriva da classi di base [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comuni, è possibile implementare eventi associati personalizzati mediante l'inclusione di alcuni metodi del modello nella classe e l'uso di metodi di utilità già presenti nelle classi di base.  
  
 Il modello è il seguente:  
  
- Metodo che **aggiungeil gestore EventName** con due parametri. Il primo parametro è l'istanza di a cui viene aggiunto il gestore eventi. Il secondo parametro è il gestore eventi da aggiungere. Il metodo deve essere `public` e `static`, senza alcun valore restituito.  
  
- Metodo **Remove*EventName*handler** con due parametri. Il primo parametro è l'istanza da cui viene rimosso il gestore eventi. Il secondo parametro è il gestore eventi da rimuovere. Il metodo deve essere `public` e `static`, senza alcun valore restituito.  
  
 Il metodo della funzione di accesso del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] **gestore Add*EventName*** facilita l'elaborazione quando gli attributi del gestore eventi associati sono dichiarati su un elemento. Anche i metodi **Add*EventName*handler** e **Remove*EventName*handler** abilitano l'accesso al codice all'archivio del gestore eventi per l'evento associato.  
  
 Questo modello generale non è ancora sufficientemente preciso per l'implementazione pratica in un framework, perché qualsiasi implementazione del lettore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specificata può avere schemi diversi per l'identificazione di eventi sottostanti nel linguaggio e nell'architettura di supporto. Questo è uno dei motivi per cui [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa gli eventi associati come eventi indirizzati; l'identificatore da usare per un evento<xref:System.Windows.RoutedEvent>() [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è già definito dal sistema di eventi. Il routing di un evento, inoltre, è una naturale estensione dell'implementazione nel concetto di evento associato al livello di linguaggio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 L'implementazione dell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aggiunta del **gestore*EventName*** per un evento <xref:System.Windows.UIElement.AddHandler%2A> associato è costituita dalla chiamata di con l'evento indirizzato e il gestore come argomenti.  
  
 Questa strategia di implementazione e il sistema di eventi indirizzati in generale limitano la gestione degli <xref:System.Windows.UIElement> eventi associati a <xref:System.Windows.ContentElement> classi derivate o classi derivate, perché solo le classi hanno <xref:System.Windows.UIElement.AddHandler%2A> implementazioni.  
  
 Ad esempio, il codice seguente definisce l'evento associato `NeedsCleaning` per la classe del proprietario `Aquarium`, usando la strategia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di dichiarazione dell'evento associato come evento indirizzato.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Si noti che il metodo usato per stabilire il campo dell'identificatore di <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>evento associato,, è in realtà lo stesso metodo usato per registrare un evento indirizzato non collegato. Gli eventi associati e gli eventi indirizzati vengono tutti registrati in un archivio interno centralizzato. Questa implementazione dell'archivio degli eventi consente la considerazione del concetto di "eventi come interfaccia" presentata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generazione di un evento associato WPF  
 Non è in genere necessario generare dal codice eventi associati esistenti definiti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questi eventi seguono il modello concettuale generale "Service" e le classi di servizio <xref:System.Windows.Input.InputManager> , ad esempio, sono responsabili della generazione degli eventi.  
  
 Tuttavia, se si definisce un evento associato personalizzato basato sul [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di base degli eventi associati in <xref:System.Windows.RoutedEvent>, è possibile usare <xref:System.Windows.UIElement.RaiseEvent%2A> per generare un evento associato da qualsiasi <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement>. Per generare un evento indirizzato (collegato o meno), è necessario dichiarare un particolare elemento nell'albero degli elementi come origine evento; tale origine viene segnalata come <xref:System.Windows.UIElement.RaiseEvent%2A> chiamante. È responsabilità del servizio determinare quale elemento viene riportato come origine nell'albero.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
