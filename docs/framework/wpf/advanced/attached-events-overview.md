---
title: Cenni preliminari sugli eventi associati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfe0d97b86a27859d79685e035d8f3f765a965b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="attached-events-overview"></a>Cenni preliminari sugli eventi associati
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definisce un componente del linguaggio e un tipo di evento noto come *evento associato*. Il concetto di evento associato consente di aggiungere un gestore per un determinato evento a un elemento arbitrario, anziché a un elemento che definisce o eredita effettivamente l'evento. In questo caso, né l'oggetto che genera potenzialmente l'evento, né l'istanza di gestione di destinazione definisce o possiede in altro modo l'evento.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone di aver letto [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md) e [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Sintassi per gli eventi associati  
 Per supportare l'uso degli eventi associati, è necessario che il codice sottostante usi una sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e un modello di codifica specifici di tali eventi.  
  
 Nella sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], l'evento associato non viene specificato solo tramite il nome dell'evento, ma con il tipo proprietario e il nome dell'evento, separati da un punto (.). Dato che il nome di evento è qualificato con il nome del tipo proprietario, la sintassi dell'evento associato consente l'associazione di tale evento a qualsiasi elemento di cui è possibile creare un'istanza.  
  
 Ad esempio, di seguito viene illustrata la sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per collegare un gestore per un evento associato `NeedsCleaning`:  
  
 [!code-xaml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Si noti il prefisso `aqua:`, necessario in questo caso perché l'evento associato è un evento personalizzato tratto da un xmlns mappato personalizzato.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Modalità di implementazione degli eventi associati in WPF  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], collegati sono supportati gli eventi da un <xref:System.Windows.RoutedEvent> campo e vengono indirizzate attraverso la struttura ad albero dopo essere stati generati. In genere, l'origine dell'evento associato (oggetto che genera l'evento) è un'origine di sistema o servizio e l'oggetto che esegue il codice che genera l'evento non è pertanto parte diretta dell'albero degli elementi.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Scenari per gli eventi associati  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], collegati gli eventi sono presenti in alcune aree di funzionalità in cui è presente astrazione del livello di servizio, ad esempio per gli eventi abilitati per il metodo statico <xref:System.Windows.Input.Mouse> classe o <xref:System.Windows.Controls.Validation> classe. Le classi che interagiscono con il servizio o lo usano possono usano l'evento nella sintassi dell'evento associato o scegliere di usarlo come un evento indirizzato che fa parte del modo in cui la classe integra le funzionalità del servizio.  
  
 Anche se in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono definiti vari eventi associati, gli scenari in cui si usa o si gestisce direttamente l'evento associato sono molto limitati. Generalmente, l'evento associato assolve uno scopo nell'architettura, ma viene inoltrato a un evento indirizzato non associato, supportato da un "wrapper" di eventi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  
  
 Ad esempio, l'evento associato sottostante <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> può più essere gestito facilmente in un dato <xref:System.Windows.UIElement> utilizzando <xref:System.Windows.UIElement.MouseDown> su quel <xref:System.Windows.UIElement> anziché utilizzare la sintassi dell'evento sia in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o codice. L'evento associato assolve a uno scopo nell'architettura perché consente l'espansione futura dei dispositivi di input. Il dispositivo ipotetico solo necessario generare <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> per simulare l'input del mouse e non è necessario derivare da <xref:System.Windows.Input.Mouse> a tale scopo. Questo scenario comporta tuttavia la gestione di codice degli eventi e la gestione di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dell'evento associato non è attinente a questo scenario.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Gestione di un evento associato in WPF  
 Il processo di gestione di un evento associato e il codice del gestore che verrà scritto è fondamentalmente lo stesso necessario per un evento indirizzato.  
  
 In genere, un evento associato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non è molto diverso da un evento indirizzato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Le differenze sono date dalla modalità di origine dell'evento e della relativa esposizione da parte di una classe come membro, operazione che ha anche effetto sulla sintassi del gestore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Tuttavia, come indicato in precedenza, gli eventi associati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti non sono destinati in modo particolare alla gestione in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Più spesso, lo scopo dell'evento è quello di consentire la segnalazione di uno stato da parte di un elemento composto a un elemento padre nella composizione, nel qual caso l'evento viene in genere generato nel codice e si basa inoltre sulla gestione della classe nella classe padre rilevante. Ad esempio, gli elementi all'interno di un <xref:System.Windows.Controls.Primitives.Selector> dovrà generare collegato <xref:System.Windows.Controls.Primitives.Selector.Selected> evento, che viene quindi gestito dal <xref:System.Windows.Controls.Primitives.Selector> classe e potenzialmente convertito dal <xref:System.Windows.Controls.Primitives.Selector> classe in un evento indirizzato diverso, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> . Per altre informazioni sugli eventi indirizzati e sulla gestione delle classi, vedere [Contrassegno degli eventi indirizzati come gestiti e gestione delle classi](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Definizione di eventi associati personalizzati come eventi indirizzati  
 Se si deriva da classi di base [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comuni, è possibile implementare eventi associati personalizzati mediante l'inclusione di alcuni metodi del modello nella classe e l'uso di metodi di utilità già presenti nelle classi di base.  
  
 Il modello è il seguente:  
  
-   Un metodo `Add*Handler` con due parametri. Il primo parametro deve identificare l'evento, il quale deve corrispondere ai nomi con il segno * nel nome del metodo. Il secondo parametro è il gestore da aggiungere. Il metodo deve essere pubblico e statico, senza valore restituito.  
  
-   Un metodo `Remove*Handler` con due parametri. Il primo parametro deve identificare l'evento, il quale deve corrispondere ai nomi con il segno * nel nome del metodo. Il secondo parametro è il gestore da rimuovere. Il metodo deve essere pubblico e statico, senza valore restituito.  
  
 Il metodo della funzione di accesso `Add*Handler` facilita l'elaborazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] quando su un elemento vengono dichiarati attributi del gestore dell'evento associato. I metodi `Add*Handler` e `Remove*Handler` abilitano inoltre l'accesso del codice all'archivio del gestore eventi per l'evento associato.  
  
 Questo modello generale non è ancora sufficientemente preciso per l'implementazione pratica in un framework, perché qualsiasi implementazione del lettore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specificata può avere schemi diversi per l'identificazione di eventi sottostanti nel linguaggio e nell'architettura di supporto. Si tratta di uno dei motivi che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa collegato eventi come eventi indirizzati; l'identificatore da utilizzare per un evento (<xref:System.Windows.RoutedEvent>) è già definito per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di eventi. Il routing di un evento, inoltre, è una naturale estensione dell'implementazione nel concetto di evento associato al livello di linguaggio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Il `Add*Handler` implementazione per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] evento costituito dalla chiamata di <xref:System.Windows.UIElement.AddHandler%2A> con l'evento indirizzato e il gestore come argomenti.  
  
 Questa strategia di implementazione e il sistema dell'evento indirizzato in genere limitano la gestione degli eventi associati a uno <xref:System.Windows.UIElement> classi derivate o <xref:System.Windows.ContentElement> classi derivate, poiché solo tali classi dispongono <xref:System.Windows.UIElement.AddHandler%2A> implementazioni.  
  
 Ad esempio, il codice seguente definisce l'evento associato `NeedsCleaning` per la classe del proprietario `Aquarium`, usando la strategia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di dichiarazione dell'evento associato come evento indirizzato.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Si noti che il metodo utilizzato per definire il campo Identificatore dell'evento associato, <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>, in realtà lo stesso metodo utilizzato per registrare un evento indirizzato non associato. Gli eventi associati e gli eventi indirizzati vengono tutti registrati in un archivio interno centralizzato. Questa implementazione dell'archivio degli eventi consente la considerazione del concetto di "eventi come interfaccia" presentata in [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Generazione di un evento associato WPF  
 Non è in genere necessario generare dal codice eventi associati esistenti definiti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Seguire il modello concettuale di "servizio" generale, questi eventi e le classi del servizio, ad esempio <xref:System.Windows.Input.InputManager> sono responsabili della generazione degli eventi.  
  
 Tuttavia, se si definisce un evento personalizzato in base il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di basare gli eventi associati nel <xref:System.Windows.RoutedEvent>, è possibile utilizzare <xref:System.Windows.UIElement.RaiseEvent%2A> per generare un evento associato da qualsiasi <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement>. Generare un evento indirizzato (associato o meno) richiede la dichiarazione di un particolare elemento nell'albero degli elementi come origine evento. tale origine viene segnalata come il <xref:System.Windows.UIElement.RaiseEvent%2A> chiamante. È responsabilità del servizio determinare quale elemento viene riportato come origine nell'albero.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Descrizione dettagliata della sintassi XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)  
 [Classi XAML e personalizzate per WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
