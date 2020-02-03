---
title: Code-behind e XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 212a37fb7fbcb7e66a669d96671333be793956df
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738098"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-behind e XAML in WPF
<a name="introduction"></a>Code-behind è un termine usato per descrivere il codice Unito a oggetti definiti dal markup, quando una pagina di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene compilata con markup. In questo argomento vengono descritti i requisiti per il code-behind e un meccanismo alternativo di codice inline per il codice in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Questo argomento è suddiviso nelle sezioni seguenti:  
  
- [Prerequisiti](#Prerequisites)  
  
- [Code-behind e linguaggio XAML](#codebehind_and_the_xaml_language)  
  
- [Code-behind, gestore eventi e requisiti della classe parziale in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Limitazioni del codice inline](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questo argomento si presuppone che sia stata letta la [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) e che si disponga di una conoscenza di base di CLR e della programmazione orientata a oggetti.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-behind e linguaggio XAML  
 Il linguaggio XAML include funzionalità a livello di linguaggio che consentono di associare i file di codice ai file di markup, dal lato del file di markup. In particolare, il linguaggio XAML definisce le funzionalità del linguaggio [X:Class Directive](../../../desktop-wpf/xaml-services/xclass-directive.md), [X:Subclass Directive](../../../desktop-wpf/xaml-services/xsubclass-directive.md)e [x:ClassModifier Directive](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md). Il modo esatto in cui il codice deve essere prodotto e come integrare markup e codice non fa parte del linguaggio XAML specificato. Viene lasciato a Framework come WPF per determinare come integrare il codice, come usare XAML nei modelli di applicazione e di programmazione e le azioni di compilazione o altro supporto richiesto da tutti.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-behind, gestore eventi e requisiti della classe parziale in WPF  
  
- La classe parziale deve derivare dal tipo che esegue il backup dell'elemento radice.  
  
- Si noti che, sotto il comportamento predefinito delle azioni di compilazione di compilazione del markup, è possibile lasciare vuota la derivazione nella definizione della classe parziale sul lato code-behind. Il risultato compilato presuppone che il tipo di supporto della radice della pagina sia la base per la classe parziale, anche se non è specificato. Tuttavia, basarsi su questo comportamento non è una procedura consigliata.  
  
- I gestori di eventi scritti nel code-behind devono essere metodi di istanza e non possono essere metodi statici. Questi metodi devono essere definiti dalla classe parziale nello spazio dei nomi CLR identificato da `x:Class`. Non è possibile qualificare il nome di un gestore eventi per indicare a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore di cercare un gestore eventi per il cablaggio degli eventi in un ambito di classe diverso.  
  
- Il gestore deve corrispondere al delegato per l'evento appropriato nel sistema di tipi di supporto.  
  
- Per il linguaggio di Visual Basic Microsoft, è possibile usare la parola chiave `Handles` specifica del linguaggio per associare i gestori a istanze ed eventi nella dichiarazione del gestore, anziché collegare i gestori con attributi in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Tuttavia, questa tecnica presenta alcune limitazioni perché la parola chiave `Handles` non supporta tutte le funzionalità specifiche del sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi, ad esempio alcuni scenari di eventi indirizzati o eventi associati. Per informazioni dettagliate, vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) è un elemento di direttiva definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un elemento `x:Code` direttiva può contenere codice di programmazione inline. Il codice definito inline può interagire con il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nella stessa pagina. Nell'esempio seguente viene illustrato il codice C# inline. Si noti che il codice si trova all'interno dell'elemento `x:Code` e che il codice deve essere racchiuso tra `<CDATA[`...`]]>` per eseguire l'escape del contenuto per XML, in modo che un processore di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], interpretando lo schema di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o lo schema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], non tenti di interpretare il contenuto letteralmente come XML.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitazioni del codice inline  
 È consigliabile evitare o limitare l'utilizzo del codice inline. In termini di architettura e filosofia di codifica, mantenere una separazione tra markup e code-behind mantiene i ruoli di progettazione e sviluppo molto più distinti. A un livello più tecnico, il codice che si scrive per il codice inline può essere scomodo da scrivere, perché si sta scrivendo sempre in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] classe parziale generata e può utilizzare solo i mapping degli spazi dei nomi XML predefiniti. Poiché non è possibile aggiungere istruzioni `using`, è necessario qualificare in modo completo molte delle chiamate API effettuate. I mapping [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefiniti includono la maggior parte degli spazi dei nomi CLR presenti negli assembly di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. sarà necessario qualificare completamente le chiamate ai tipi e ai membri contenuti negli altri spazi dei nomi CLR. Non è inoltre possibile definire alcunché oltre la classe parziale nel codice inline e tutte le entità del codice utente a cui si fa riferimento devono esistere come membro o variabile all'interno della classe parziale generata. Non sono inoltre disponibili altre funzionalità di programmazione specifiche del linguaggio, ad esempio macro o `#ifdef` su variabili globali o variabili di compilazione. Per altre informazioni, vedere [tipo XAML intrinseco x:code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Tipo XAML intrinseco x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [Compilazione di un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
