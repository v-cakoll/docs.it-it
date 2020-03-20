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
ms.openlocfilehash: e125c9a57090049f4319da96c7004f06606d0147
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141562"
---
# <a name="attached-events-overview"></a>Cenni preliminari sugli eventi associati

Extensible Application Markup Language (XAML)Extensible Application Markup Language (XAML) definisce un componente del linguaggio e un tipo di evento denominato *evento associato.* Il concetto di evento associato consente di aggiungere un gestore per un determinato evento a un elemento arbitrario, anziché a un elemento che definisce o eredita effettivamente l'evento. In questo caso, né l'oggetto che genera potenzialmente l'evento, né l'istanza di gestione di destinazione definisce o possiede in altro modo l'evento.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento si presuppone di aver letto [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md) e [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Syntax"></a>
## <a name="attached-event-syntax"></a>Sintassi per gli eventi associati  
 Gli eventi associati hanno una sintassi XAML e un modello di codifica che deve essere usato dal codice di supporto per supportare l'utilizzo dell'evento associato.  
  
 Nella sintassi XAML, l'evento associato viene specificato non solo dal nome dell'evento, ma dal tipo proprietario più il nome dell'evento, separato da un punto (.). Dato che il nome di evento è qualificato con il nome del tipo proprietario, la sintassi dell'evento associato consente l'associazione di tale evento a qualsiasi elemento di cui è possibile creare un'istanza.  
  
 Ad esempio, di seguito è riportata la sintassi XAML per associare un gestore per un evento associato personalizzato:For example, the following is the XAML syntax for attaching a handler for a custom `NeedsCleaning` attached event:  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Si noti il prefisso `aqua:`, necessario in questo caso perché l'evento associato è un evento personalizzato tratto da un xmlns mappato personalizzato.  
  
<a name="WPFImplements"></a>
## <a name="how-wpf-implements-attached-events"></a>Modalità di implementazione degli eventi associati in WPF

In WPFWPF, gli eventi <xref:System.Windows.RoutedEvent> associati sono supportati da un campo e vengono indirizzati attraverso la struttura ad albero dopo essere stati generati. In genere, l'origine dell'evento associato (oggetto che genera l'evento) è un'origine di sistema o servizio e l'oggetto che esegue il codice che genera l'evento non è pertanto parte diretta dell'albero degli elementi.  
  
<a name="Scenarios"></a>
## <a name="scenarios-for-attached-events"></a>Scenari per gli eventi associati  
 In WPFWPF, gli eventi associati sono presenti in determinate aree di funzionalità in cui <xref:System.Windows.Input.Mouse> è presente <xref:System.Windows.Controls.Validation> l'astrazione a livello di servizio, ad esempio per gli eventi abilitati dalla classe statica o dalla classe. Le classi che interagiscono con il servizio o lo usano possono usano l'evento nella sintassi dell'evento associato o scegliere di usarlo come un evento indirizzato che fa parte del modo in cui la classe integra le funzionalità del servizio.  
  
 Anche se WPFWPF definisce una serie di eventi associati, gli scenari in cui si utilizzerà o gestire direttamente l'evento associato sono molto limitati. In genere, l'evento associato ha uno scopo di architettura, ma viene quindi inoltrato a un evento indirizzato non associato (supportato con un evento CLR "wrapper").  
  
 Ad esempio, l'evento <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> associato sottostante può essere <xref:System.Windows.UIElement> gestito <xref:System.Windows.UIElement.MouseDown> più <xref:System.Windows.UIElement> facilmente in qualsiasi dato usandolo anziché gestire la sintassi dell'evento associato in XAML o nel codice. L'evento associato assolve a uno scopo nell'architettura perché consente l'espansione futura dei dispositivi di input. Il dispositivo ipotetico avrebbe solo <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> bisogno di sollevare al fine di simulare l'input del mouse, e non avrebbe bisogno di derivare da <xref:System.Windows.Input.Mouse> per farlo. Tuttavia, questo scenario prevede la gestione del codice degli eventi e la gestione XAML dell'evento associato non è rilevante per questo scenario.  
  
<a name="Handling"></a>
## <a name="handling-an-attached-event-in-wpf"></a>Gestione di un evento associato in WPF  
 Il processo di gestione di un evento associato e il codice del gestore che verrà scritto è fondamentalmente lo stesso necessario per un evento indirizzato.  
  
 In generale, un WPFWPF evento associato non è molto diverso da un WPFWPF evento indirizzato. Le differenze sono il modo in cui l'evento viene originato e come viene esposto da una classe come membro (che influisce anche sulla sintassi del gestore XAML).  
  
 Tuttavia, come indicato in precedenza, gli eventi associati WPFWPF esistenti non sono particolarmente destinati alla gestione in WPFWPF. Più spesso, lo scopo dell'evento è quello di consentire la segnalazione di uno stato da parte di un elemento composto a un elemento padre nella composizione, nel qual caso l'evento viene in genere generato nel codice e si basa inoltre sulla gestione della classe nella classe padre rilevante. Ad esempio, gli <xref:System.Windows.Controls.Primitives.Selector> elementi all'interno <xref:System.Windows.Controls.Primitives.Selector.Selected> di un oggetto devono generare <xref:System.Windows.Controls.Primitives.Selector> l'evento associato, <xref:System.Windows.Controls.Primitives.Selector> che viene quindi gestito <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>dalla classe e quindi potenzialmente convertiti dalla classe in un evento indirizzato diverso, . Per altre informazioni sugli eventi indirizzati e sulla gestione delle classi, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definizione di eventi associati personalizzati come eventi indirizzati  
 Se si deriva da classi di base WPFWPF comuni, è possibile implementare eventi associati personalizzati includendo determinati metodi di pattern nella classe e usando metodi di utilità già presenti nelle classi di base.  
  
 Il modello è il seguente:  
  
- Un metodo __Add*EventName*Handler__ con due parametri. Il primo parametro è l'istanza a cui viene aggiunto il gestore eventi. Il secondo parametro è il gestore eventi da aggiungere. Il metodo `public` deve `static`essere e , senza alcun valore restituito.  
  
- Un metodo __Remove*EventName*Handler__ con due parametri. Il primo parametro è l'istanza da cui viene rimosso il gestore eventi. Il secondo parametro è il gestore eventi da rimuovere. Il metodo `public` deve `static`essere e , senza alcun valore restituito.  
  
 Il __Add*EventName*Handler__ metodo della funzione di accesso facilita l'elaborazione XAML quando gli attributi del gestore eventi associati vengono dichiarati su un elemento. I metodi __Add*EventName*Handler__ e __Remove*EventName*Handler__ consentono inoltre l'accesso al codice all'archivio dei gestori eventi per l'evento associato.  
  
 Questo modello generale non è ancora sufficientemente preciso per l'implementazione pratica in un framework, perché qualsiasi implementazione del lettore XAML potrebbe avere schemi diversi per identificare gli eventi sottostanti nel linguaggio e nell'architettura di supporto. Questo è uno dei motivi per cui WPFWPF implementa gli eventi associati come eventi indirizzati; l'identificatore da utilizzare<xref:System.Windows.RoutedEvent>per un evento ( ) è già definito dal sistema di eventi WPFWPF. Inoltre, il routing di un evento è un'estensione di implementazione naturale nel concetto a livello di linguaggio XAML di un evento associato.  
  
 Il __Add*EventName*Handler__ implementazione per un <xref:System.Windows.UIElement.AddHandler%2A> WPFWPF evento associato consiste nel chiamare il con l'evento indirizzato e gestore come argomenti.  
  
 Questa strategia di implementazione e il sistema di eventi <xref:System.Windows.UIElement> indirizzati <xref:System.Windows.ContentElement> in generale limitano <xref:System.Windows.UIElement.AddHandler%2A> la gestione per gli eventi associati alle classi derivate o alle classi derivate, poiché solo tali classi dispongono di implementazioni.  
  
 Ad esempio, il codice `NeedsCleaning` seguente definisce l'evento associato nella classe `Aquarium`owner , utilizzando la strategia di evento associato WPFWPF per dichiarare l'evento associato come evento indirizzato.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Si noti che il metodo utilizzato per <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>stabilire il campo dell'identificatore di evento associato, , è in realtà lo stesso metodo utilizzato per registrare un evento indirizzato non associato. Gli eventi associati e gli eventi indirizzati vengono tutti registrati in un archivio interno centralizzato. Questa implementazione dell'archivio degli eventi consente la considerazione del concetto di "eventi come interfaccia" presentata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
<a name="Raising"></a>
## <a name="raising-a-wpf-attached-event"></a>Generazione di un evento associato WPF  
 In genere non è necessario generare eventi associati definiti da WPF esistenti dal codice. Questi eventi seguono il modello concettuale generale <xref:System.Windows.Input.InputManager> "servizio" e le classi di servizio, ad esempio responsabili della generazione degli eventi.  
  
 Tuttavia, se si definisce un evento associato personalizzato basato sul <xref:System.Windows.RoutedEvent>modello WPF <xref:System.Windows.UIElement.RaiseEvent%2A> di basare gli <xref:System.Windows.UIElement> eventi <xref:System.Windows.ContentElement>associati su , è possibile utilizzare per generare un evento associato da qualsiasi o . La generazione di un evento indirizzato (associato o meno) richiede la dichiarazione di un particolare elemento nella struttura ad albero dell'elemento come origine dell'evento. tale origine viene <xref:System.Windows.UIElement.RaiseEvent%2A> segnalata come chiamante. È responsabilità del servizio determinare quale elemento viene riportato come origine nell'albero.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
