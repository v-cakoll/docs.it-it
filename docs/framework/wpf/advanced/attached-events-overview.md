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
ms.openlocfilehash: 76ff60cfe26f9105d4504164802987115fc2a7e2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455468"
---
# <a name="attached-events-overview"></a>Cenni preliminari sugli eventi associati

Extensible Application Markup Language (XAML) definisce un componente del linguaggio e un tipo di evento chiamato *evento associato*. Il concetto di evento associato consente di aggiungere un gestore per un determinato evento a un elemento arbitrario, anziché a un elemento che definisce o eredita effettivamente l'evento. In questo caso, né l'oggetto che genera potenzialmente l'evento, né l'istanza di gestione di destinazione definisce o possiede in altro modo l'evento.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento si presuppone di aver letto [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md) e [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Sintassi per gli eventi associati  
 Gli eventi associati hanno una sintassi XAML e uno schema di codifica che deve essere usato dal codice di supporto per supportare l'utilizzo dell'evento associato.  
  
 Nella sintassi XAML, l'evento associato viene specificato non solo dal nome dell'evento, ma dal tipo proprietario più il nome dell'evento, separato da un punto (.). Dato che il nome di evento è qualificato con il nome del tipo proprietario, la sintassi dell'evento associato consente l'associazione di tale evento a qualsiasi elemento di cui è possibile creare un'istanza.  
  
 Ad esempio, di seguito è riportata la sintassi XAML per collegare un gestore per un evento associato `NeedsCleaning` personalizzato:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Si noti il prefisso `aqua:`, necessario in questo caso perché l'evento associato è un evento personalizzato tratto da un xmlns mappato personalizzato.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Modalità di implementazione degli eventi associati in WPF

In WPF gli eventi associati sono supportati da un campo <xref:System.Windows.RoutedEvent> e vengono instradati attraverso la struttura ad albero dopo la generazione. In genere, l'origine dell'evento associato (oggetto che genera l'evento) è un'origine di sistema o servizio e l'oggetto che esegue il codice che genera l'evento non è pertanto parte diretta dell'albero degli elementi.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Scenari per gli eventi associati  
 In WPF gli eventi associati sono presenti in determinate aree di funzionalità in cui è presente un'astrazione a livello di servizio, ad esempio per gli eventi abilitati dalla classe <xref:System.Windows.Input.Mouse> statica o dalla classe <xref:System.Windows.Controls.Validation>. Le classi che interagiscono con il servizio o lo usano possono usano l'evento nella sintassi dell'evento associato o scegliere di usarlo come un evento indirizzato che fa parte del modo in cui la classe integra le funzionalità del servizio.  
  
 Sebbene WPF definisca un certo numero di eventi associati, gli scenari in cui si utilizzerà o si gestirà direttamente l'evento associato sono molto limitati. In genere, l'evento associato serve a scopo di architettura, ma viene quindi inoltrato a un evento indirizzato non associato (supportato con un evento CLR "wrapper").  
  
 Ad esempio, l'evento associato sottostante <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> può essere gestito più facilmente in qualsiasi <xref:System.Windows.UIElement> specificato utilizzando <xref:System.Windows.UIElement.MouseDown> su tale <xref:System.Windows.UIElement> anziché gestire la sintassi degli eventi associati in XAML o nel codice. L'evento associato assolve a uno scopo nell'architettura perché consente l'espansione futura dei dispositivi di input. Il dispositivo ipotetico deve solo generare <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> per simulare l'input del mouse e non deve derivare da <xref:System.Windows.Input.Mouse> a tale scopo. Tuttavia, questo scenario implica la gestione del codice degli eventi e la gestione XAML dell'evento associato non è pertinente per questo scenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Gestione di un evento associato in WPF  
 Il processo di gestione di un evento associato e il codice del gestore che verrà scritto è fondamentalmente lo stesso necessario per un evento indirizzato.  
  
 In generale, un evento associato WPF non è molto diverso da un evento indirizzato WPF. Le differenze sono il modo in cui l'evento viene originato e il modo in cui viene esposto da una classe come membro (che influiscono anche sulla sintassi del gestore XAML).  
  
 Tuttavia, come indicato in precedenza, gli eventi associati WPF esistenti non sono destinati in modo specifico alla gestione in WPF. Più spesso, lo scopo dell'evento è quello di consentire la segnalazione di uno stato da parte di un elemento composto a un elemento padre nella composizione, nel qual caso l'evento viene in genere generato nel codice e si basa inoltre sulla gestione della classe nella classe padre rilevante. Ad esempio, è previsto che gli elementi all'interno di un <xref:System.Windows.Controls.Primitives.Selector> generino l'evento Attached <xref:System.Windows.Controls.Primitives.Selector.Selected>, che è quindi gestito dalla classe <xref:System.Windows.Controls.Primitives.Selector> e quindi potenzialmente convertito dalla classe <xref:System.Windows.Controls.Primitives.Selector> in un evento indirizzato diverso, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Per altre informazioni sugli eventi indirizzati e sulla gestione delle classi, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definizione di eventi associati personalizzati come eventi indirizzati  
 Se si esegue la derivazione da classi base WPF comuni, è possibile implementare eventi allegati personalizzati includendo determinati metodi di modello nella classe e usando metodi di utilità già presenti nelle classi di base.  
  
 Il modello è il seguente:  
  
- Metodo che __aggiunge il gestore*EventName*__ con due parametri. Il primo parametro è l'istanza di a cui viene aggiunto il gestore eventi. Il secondo parametro è il gestore eventi da aggiungere. Il metodo deve essere `public` e `static`, senza alcun valore restituito.  
  
- Metodo __Remove*EventName*handler__ con due parametri. Il primo parametro è l'istanza da cui viene rimosso il gestore eventi. Il secondo parametro è il gestore eventi da rimuovere. Il metodo deve essere `public` e `static`, senza alcun valore restituito.  
  
 Il metodo della funzione di accesso del __gestore Add*EventName*__ facilita l'elaborazione XAML quando gli attributi del gestore eventi associati sono dichiarati su un elemento. Anche i metodi __Add*EventName*handler__ e __Remove*EventName*handler__ abilitano l'accesso al codice all'archivio del gestore eventi per l'evento associato.  
  
 Questo modello generale non è ancora abbastanza preciso per l'implementazione pratica in un Framework, perché qualsiasi implementazione del reader XAML potrebbe avere schemi diversi per l'identificazione degli eventi sottostanti nel linguaggio e nell'architettura di supporto. Questo è uno dei motivi per cui WPF implementa gli eventi associati come eventi indirizzati. l'identificatore da utilizzare per un evento (<xref:System.Windows.RoutedEvent>) è già definito dal sistema di eventi WPF. Inoltre, il routing di un evento è un'estensione di implementazione naturale nel concetto a livello di linguaggio XAML di un evento associato.  
  
 L'implementazione dell' __aggiunta del gestore*EventName*__ per un evento associato WPF consiste nella chiamata di <xref:System.Windows.UIElement.AddHandler%2A> con l'evento indirizzato e il gestore come argomenti.  
  
 Questa strategia di implementazione e il sistema di eventi indirizzati in generale limitano la gestione degli eventi associati a <xref:System.Windows.UIElement> classi derivate o <xref:System.Windows.ContentElement> classi derivate, perché solo le classi dispongono di implementazioni di <xref:System.Windows.UIElement.AddHandler%2A>.  
  
 Il codice seguente, ad esempio, definisce il `NeedsCleaning` evento associato sulla classe Owner `Aquarium`, usando la strategia di evento associato WPF di dichiarazione dell'evento associato come un evento indirizzato.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Si noti che il metodo usato per stabilire il campo dell'identificatore di evento associato, <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>, è in realtà lo stesso metodo usato per registrare un evento indirizzato non collegato. Gli eventi associati e gli eventi indirizzati vengono tutti registrati in un archivio interno centralizzato. Questa implementazione dell'archivio degli eventi consente la considerazione del concetto di "eventi come interfaccia" presentata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generazione di un evento associato WPF  
 Non è in genere necessario generare eventi allegati esistenti definiti da WPF dal codice. Questi eventi seguono il modello concettuale generale "Service" e le classi di servizio come <xref:System.Windows.Input.InputManager> sono responsabili della generazione degli eventi.  
  
 Tuttavia, se si definisce un evento associato personalizzato basato sul modello WPF di eventi associati basandoli in <xref:System.Windows.RoutedEvent>, è possibile usare <xref:System.Windows.UIElement.RaiseEvent%2A> per generare un evento associato da qualsiasi <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement>. Per generare un evento indirizzato (collegato o meno), è necessario dichiarare un particolare elemento nell'albero degli elementi come origine evento; tale origine viene segnalata come il chiamante del <xref:System.Windows.UIElement.RaiseEvent%2A>. È responsabilità del servizio determinare quale elemento viene riportato come origine nell'albero.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
