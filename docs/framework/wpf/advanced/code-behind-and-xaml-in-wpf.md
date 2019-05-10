---
title: Code-behind e XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 01122991e99e41259c3b83a38eba002734d749ee
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655522"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-behind e XAML in WPF
<a name="introduction"></a> Code-behind è un termine usato per descrivere il codice che è unita in join con gli oggetti definiti da commenti quando una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina viene compilato dal markup. In questo argomento vengono descritti i requisiti per il code-behind, nonché un meccanismo di codice inline alternativo per il codice in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Prerequisiti](#Prerequisites)  
  
- [Code-Behind e il linguaggio XAML](#codebehind_and_the_xaml_language)  
  
- [Code-behind, gestore eventi e requisiti della classe parziale in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [X:code](#x_Code)  
  
- [Limitazioni del codice inline](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questo argomento si presuppone di aver letto la [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md) e hanno una conoscenza di base del [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] e della programmazione orientata agli oggetti.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-Behind e il linguaggio XAML  
 Il linguaggio XAML include funzionalità a livello di linguaggio che consentono di associare i file di codice con i file di markup, del lato di file di markup. In particolare, il linguaggio XAML definisce le funzionalità del linguaggio [direttiva X:Class](../../xaml-services/x-class-directive.md), [direttiva X:Subclass](../../xaml-services/x-subclass-directive.md), e [direttiva X:ClassModifier](../../xaml-services/x-classmodifier-directive.md). Esattamente come dovrebbe essere generato il codice e come integrare markup e codice, non fa parte di ciò che specifica il linguaggio XAML. Viene eseguito fino al livello di Framework, ad esempio WPF per determinare come integrare il codice, come utilizzare XAML nell'applicazione e i modelli di programmazione e la compilazione azioni o altro supporto che tutto questo richiede.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-behind, gestore eventi e requisiti della classe parziale in WPF  
  
- La classe parziale deve derivare dal tipo sottostante dell'elemento radice.  
  
- Si noti che in base al comportamento predefinito di azioni di compilazione di markup, è possibile lasciare vuota la derivazione nella definizione di classe parziale sul lato code-behind. Il risultato compilato presupporrà che il tipo sottostante della radice della pagina per essere usato come base per la classe parziale, anche se non specificato. Tuttavia, basarsi su questo comportamento non è consigliata.  
  
- I gestori di eventi che si scrive nel code-behind devono essere metodi di istanza e non possono essere metodi statici. Questi metodi devono essere definiti dalla classe parziale nello spazio dei nomi CLR identificato da `x:Class`. Non è possibile qualificare il nome di un gestore eventi per indicare un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore per cercare un gestore eventi per il collegamento di eventi in un ambito di classe diversa.  
  
- Il gestore deve corrispondere il delegato per l'evento appropriato nel sistema dei tipi sottostante.  
  
- Per la lingua di Microsoft Visual Basic in particolare, è possibile usare le specifiche della lingua `Handles` parola chiave da associare gestori istanze ed eventi nella dichiarazione del gestore, invece di collegare i gestori con gli attributi in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Questa tecnica presenta tuttavia alcune limitazioni perché il `Handles` parola chiave in grado di supportare tutte le funzionalità specifiche del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di eventi, ad esempio alcuni scenari di eventi indirizzati o gli eventi associati. Per informazioni dettagliate, vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>X:code  
 [X:code](../../xaml-services/x-code-intrinsic-xaml-type.md) viene definito un elemento della direttiva [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Un `x:Code` direttiva elemento può contenere il codice di programmazione inline. Il codice che viene definito inline può interagire con il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nella stessa pagina. L'esempio seguente illustra codice c# inline. Si noti che il codice si trova all'interno di `x:Code` elemento e che il codice deve essere racchiusa tra parentesi `<CDATA[`... `]]>` per eseguire l'escape del contenuto per [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], in modo che un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore (interpretazione di uno il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema o i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] schema) non tenterà di interpretare il contenuto letteralmente come [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitazioni del codice inline  
 È consigliabile evitare o limitare l'uso di codice inline. In termini di architettura e codifica, mantenendo una separazione tra markup e code-behind mantiene i ruoli per gli sviluppatori e designer molto più distinti. A un livello più tecnico, il codice scritto per il codice inline può essere difficile, perché vengono sempre scritte nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] classe parziale generata e possono usare solo il mapping dello spazio dei nomi XML predefinito. Poiché non è possibile aggiungere `using` (istruzioni), è necessario qualificare numerose il [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] le chiamate effettuate. Il valore predefinito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mapping includono la maggior parte ma non tutte [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] spazi dei nomi presenti nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly, sarà necessario qualificare completamente le chiamate a tipi e membri contenuti all'interno di altri spazi dei nomi CLR. È anche possibile definire nient'altro che la classe parziale nel codice inline e si fa riferimento a tutte le entità di codice utente devono esistere come un membro o una variabile all'interno della classe parziale generata. Altre funzionalità specifiche del linguaggio programmazione, ad esempio le macro o `#ifdef` nelle variabili globali o le variabili di compilazione, non sono disponibili. Per altre informazioni, vedere [tipo XAML intrinseco X:code](../../xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Tipo XAML intrinseco x:Code](../../xaml-services/x-code-intrinsic-xaml-type.md)
- [Compilazione di un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
