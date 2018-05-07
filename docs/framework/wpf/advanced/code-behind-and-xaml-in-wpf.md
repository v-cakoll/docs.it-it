---
title: Code-behind e XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 09d4f010ca53c5e3d2d9dede172e7ae2102261b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-behind e XAML in WPF
<a name="introduction"></a> Code-behind è un termine usato per descrivere il codice che viene unito con oggetti definiti dal markup, quando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina viene compilato dal markup. In questo argomento vengono descritti i requisiti per il code-behind, nonché un meccanismo di codice inline alternativo per il codice in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Prerequisiti](#Prerequisites)  
  
-   [Code-Behind e il linguaggio XAML](#codebehind_and_the_xaml_language)  
  
-   [Code-behind, gestore eventi e i requisiti di classe parziale in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [X:code](#x_Code)  
  
-   [Limitazioni del codice inline](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento si presuppone di avere letto il [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) e avere una conoscenza di base di [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] e programmazione orientata a oggetti.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind e il linguaggio XAML  
 Il linguaggio XAML include le funzionalità a livello di linguaggio che consentono di associare i file di codice con i file di markup, dal lato del file di markup. In particolare, il linguaggio XAML definisce le funzionalità del linguaggio [direttiva X:Class](../../../../docs/framework/xaml-services/x-class-directive.md), [direttiva X:Subclass](../../../../docs/framework/xaml-services/x-subclass-directive.md), e [direttiva X:ClassModifier](../../../../docs/framework/xaml-services/x-classmodifier-directive.md). Esattamente come il codice deve essere prodotta e come integrare markup e il codice non fa parte di ciò che specifica il linguaggio XAML. È compito del Framework, ad esempio WPF per determinare la modalità di integrazione del codice, come da usare è XAML nell'applicazione e i modelli di programmazione e la compilazione azioni o altro supporto che tutto ciò richiede.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-behind, gestore eventi e i requisiti di classe parziale in WPF  
  
-   La classe parziale deve derivare dal tipo che supporta l'elemento radice.  
  
-   Si noti che con il comportamento predefinito di azioni di compilazione di markup, è possibile lasciare vuota la derivazione nella definizione di classe parziale sul lato di codice. Il risultato compilato presuppone che il tipo di supporto della radice della pagina per essere la base per la classe parziale, anche se non specificato. Tuttavia, basarsi su questo comportamento non è consigliata.  
  
-   I gestori di eventi che si scrive nel code-behind devono essere metodi di istanza e non possono essere metodi statici. Questi metodi devono essere definiti dalla classe parziale nello spazio dei nomi CLR identificato da `x:Class`. Non è possibile qualificare il nome di un gestore eventi per indicare un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore di cercare un gestore eventi per il collegamento di eventi in un ambito di classe diversa.  
  
-   Il gestore deve corrispondere il delegato per l'evento appropriato nel sistema di tipi di backup.  
  
-   Per la lingua di Microsoft Visual Basic in particolare, è possibile utilizzare la specifica della lingua `Handles` parola chiave da associare gestori eventi nella dichiarazione del gestore, anziché associare gestori di eventi con gli attributi e le istanze [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Tuttavia, questa tecnica presenta alcune limitazioni perché il `Handles` (parola chiave) non supporta tutte le funzionalità specifiche del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di eventi, ad esempio alcuni scenari di eventi indirizzati o gli eventi associati. Per informazioni dettagliate, vedere [Visual Basic e la gestione degli eventi di WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>X:code  
 [X:code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) è un elemento della direttiva definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un `x:Code` direttiva elemento può contenere codice di programmazione inline. Il codice che viene definito inline può interagire con il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nella stessa pagina. Nell'esempio seguente viene illustrato il codice c# inline. Si noti che il codice si trova all'interno di `x:Code` elemento e che il codice deve essere racchiusa tra parentesi `<CDATA[`... `]]>` per eseguire l'escape del contenuto per [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], in modo che un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore (interpretazione sia il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] schema) non tenterà di interpretare il contenuto letteralmente come [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitazioni del codice inline  
 È consigliabile evitare o limitare l'utilizzo di codice inline. In termini di architettura e codifica, la gestione di una separazione tra markup e code-behind mantiene i ruoli di progettazione e sviluppo più distinti. A un livello più tecnico, il codice scritto per il codice inline può essere difficile, perché vengono sempre scritte nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] classe parziale generata e possono usare solo il mapping dello spazio dei nomi XML predefinito. Poiché non è possibile aggiungere `using` istruzioni, è necessario qualificare molti il [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] chiamate effettuate. Il valore predefinito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mapping includono la maggior parte ma non tutte [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] gli spazi dei nomi che sono presenti nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] degli assembly, è necessario qualificare completamente le chiamate a tipi e membri contenuti all'interno di altri spazi dei nomi CLR. È inoltre possibile definire qualsiasi elemento che la classe parziale nel codice inline e si fa riferimento a tutte le entità di codice utente deve esistere come un membro o una variabile all'interno della classe parziale generata. Altre funzionalità specifiche del linguaggio programmazione, ad esempio le macro o `#ifdef` nelle variabili globali o variabili di compilazione, non sono disponibili. Per ulteriori informazioni, vedere [tipo XAML intrinseco X:code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Tipo XAML intrinseco x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [Compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Descrizione dettagliata della sintassi XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
