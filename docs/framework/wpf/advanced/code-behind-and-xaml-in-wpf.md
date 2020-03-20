---
title: Code-behind e XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145345"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-behind e XAML in WPF
<a name="introduction"></a>Code-behind è un termine utilizzato per descrivere il codice unito [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a oggetti definiti dal markup, quando una pagina viene compilata tramite markup. In questo argomento vengono descritti i requisiti per il code-behind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e un meccanismo alternativo del codice inline per il codice in .  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Prerequisiti](#Prerequisites)  
  
- [Code-behind e linguaggio XAML](#codebehind_and_the_xaml_language)  
  
- [Code-behind, Event Handler, and Partial Class Requirements in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Codice](#x_Code)  
  
- [Limitazioni del codice inlineInline Code Limitations](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 In questo argomento si presuppone che sia stata letta la cenni preliminari [su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) e che siano disponibili alcune conoscenze di base su CLR e sulla programmazione orientata agli oggetti.  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>Code-behind e linguaggio XAML  
 Il linguaggio XAML include funzionalità a livello di linguaggio che consentono di associare file di codice ai file di markup dal lato del file di markup. In particolare, il linguaggio XAML definisce la [direttiva x:Class](../../../desktop-wpf/xaml-services/xclass-directive.md)delle funzionalità del linguaggio , [x:Subclass Directive](../../../desktop-wpf/xaml-services/xsubclass-directive.md)e [x:ClassModifier Directive](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md). Esattamente come deve essere prodotto il codice e come integrare il markup e il codice, non fa parte di ciò che specifica il linguaggio XAML. È lasciato a framework come WPFWPF per determinare come integrare il codice, come usare XAML nei modelli di applicazione e programmazione e le azioni di compilazione o altro supporto che tutto questo richiede.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-behind, Event Handler, and Partial Class Requirements in WPF  
  
- La classe parziale deve derivare dal tipo che supporta l'elemento radice.  
  
- Si noti che nel comportamento predefinito delle azioni di compilazione del markup, è possibile lasciare la derivazione vuota nella definizione della classe parziale sul lato code-behind. Il risultato compilato presupporrà che il tipo di supporto della radice della pagina sia la base per la classe parziale, anche se non specificato. Tuttavia, basarsi su questo comportamento non è una procedura consigliata.  
  
- I gestori eventi scritti nel code-behind devono essere metodi di istanza e non possono essere metodi statici. Questi metodi devono essere definiti dalla classe parziale all'interno dello spazio dei nomi CLR identificato da `x:Class`. Non è possibile qualificare il nome [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di un gestore eventi per indicare a un processore di cercare un gestore eventi per il cablaggio dell'evento in un ambito di classe diverso.  
  
- Il gestore deve corrispondere al delegato per l'evento appropriato nel sistema di tipi di supporto.  
  
- Per il linguaggio Microsoft Visual Basic in `Handles` particolare, è possibile utilizzare la parola chiave specifica del linguaggio per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]associare gestori a istanze ed eventi nella dichiarazione del gestore, anziché associare gestori con attributi in . Tuttavia, questa tecnica presenta alcune `Handles` limitazioni perché la parola [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiave non supporta tutte le funzionalità specifiche del sistema di eventi, ad esempio determinati scenari di eventi indirizzati o eventi associati. Per informazioni dettagliate, vedere Gestione degli eventi di [Visual Basic e WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>
## <a name="xcode"></a>x:Codice  
 [x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) è un elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]direttiva definito in . Un `x:Code` elemento direttiva può contenere codice di programmazione inline. Il codice definito inline può [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] interagire con la stessa pagina. Nell'esempio seguente viene illustrato il codice inline di C. Si noti che `x:Code` il codice è all'interno `<CDATA[`dell'elemento e che il codice deve essere circondato da ... `]]>` per eseguire l'escape del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contenuto di XML, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modo che un processore (interpretando lo schema o lo schema) non tenterà di interpretare il contenuto letteralmente come XML.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>Limitazioni del codice inlineInline Code Limitations  
 È consigliabile evitare o limitare l'utilizzo di codice inline. In termini di architettura e filosofia di codifica, mantenere una separazione tra markup e code-behind mantiene i ruoli di progetti progettisti e sviluppatori molto più distinti. A un livello più tecnico, il codice scritto per il codice inline può [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] essere scomodo da scrivere, perché si scrive sempre nella classe parziale generata e può utilizzare solo i mapping dello spazio dei nomi XML predefinito. Poiché non `using` è possibile aggiungere istruzioni, è necessario qualificare completamente molte delle chiamate API effettuate. I [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mapping predefiniti includono la maggior parte ma non [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tutti gli spazi dei nomi CLR presenti negli assembly; sarà necessario qualificare completamente le chiamate a tipi e membri contenuti negli altri spazi dei nomi CLR. Non è inoltre possibile definire elementi oltre la classe parziale nel codice inline e tutte le entità di codice utente a cui si fa riferimento devono esistere come membro o variabile all'interno della classe parziale generata. Altre funzionalità di programmazione specifiche `#ifdef` del linguaggio, ad esempio macro o contro variabili globali o variabili di compilazione, non sono disponibili. Per ulteriori informazioni, vedere [Tipo XAML intrinseco x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Tipo XAML intrinseco x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Compilazione di un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
