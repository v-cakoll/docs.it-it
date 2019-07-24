---
title: Code-behind e XAML in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: acd8c9ff0a4ff718dba272958a3e63820bcf1354
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401617"
---
# <a name="code-behind-and-xaml-in-wpf"></a>Code-behind e XAML in WPF
<a name="introduction"></a>Code-behind è un termine usato per descrivere il codice Unito a oggetti definiti dal markup, quando una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina viene compilata con markup. In questo argomento vengono descritti i requisiti per il code-behind e un meccanismo alternativo di codice inline [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]per il codice in.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Prerequisiti](#Prerequisites)  
  
- [Code-behind e linguaggio XAML](#codebehind_and_the_xaml_language)  
  
- [Code-behind, gestore eventi e requisiti della classe parziale in WPF](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [Limitazioni del codice inline](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 In questo argomento si presuppone che sia stata letta la [Panoramica di XAML (WPF)](xaml-overview-wpf.md) e che si disponga di una conoscenza di base di CLR e della programmazione orientata a oggetti.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>Code-behind e linguaggio XAML  
 Il linguaggio XAML include funzionalità a livello di linguaggio che consentono di associare i file di codice ai file di markup, dal lato del file di markup. In particolare, il linguaggio XAML definisce le funzionalità del linguaggio [X:Class Directive](../../xaml-services/x-class-directive.md), [X:Subclass Directive](../../xaml-services/x-subclass-directive.md)e [x:ClassModifier Directive](../../xaml-services/x-classmodifier-directive.md). Il modo esatto in cui il codice deve essere prodotto e come integrare markup e codice non fa parte del linguaggio XAML specificato. Viene lasciato a Framework come WPF per determinare come integrare il codice, come usare XAML nei modelli di applicazione e di programmazione e le azioni di compilazione o altro supporto richiesto da tutti.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>Code-behind, gestore eventi e requisiti della classe parziale in WPF  
  
- La classe parziale deve derivare dal tipo che esegue il backup dell'elemento radice.  
  
- Si noti che, sotto il comportamento predefinito delle azioni di compilazione di compilazione del markup, è possibile lasciare vuota la derivazione nella definizione della classe parziale sul lato code-behind. Il risultato compilato presuppone che il tipo di supporto della radice della pagina sia la base per la classe parziale, anche se non è specificato. Tuttavia, basarsi su questo comportamento non è una procedura consigliata.  
  
- I gestori di eventi scritti nel code-behind devono essere metodi di istanza e non possono essere metodi statici. Questi metodi devono essere definiti dalla classe parziale nello spazio dei nomi CLR identificato da `x:Class`. Non è possibile qualificare il nome di un gestore eventi per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] indicare a un processore di cercare un gestore eventi per il cablaggio degli eventi in un ambito di classe diverso.  
  
- Il gestore deve corrispondere al delegato per l'evento appropriato nel sistema di tipi di supporto.  
  
- Per il linguaggio di Visual Basic Microsoft, è possibile usare la parola chiave specifica `Handles` del linguaggio per associare i gestori a istanze ed eventi nella dichiarazione del gestore, anziché collegare i gestori con attributi in. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Tuttavia, questa tecnica presenta alcune limitazioni perché la `Handles` parola chiave non può supportare tutte le funzionalità specifiche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del sistema di eventi, ad esempio determinati scenari di eventi indirizzati o eventi associati. Per informazioni dettagliate, vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:code](../../xaml-services/x-code-intrinsic-xaml-type.md) è un elemento di direttiva definito [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]in. Un `x:Code` elemento Directive può contenere codice di programmazione inline. Il codice definito inline può interagire con l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] nella stessa pagina. Nell'esempio seguente viene illustrato il codice C# inline. Si noti che il codice si trova `x:Code` all'interno dell'elemento e che il codice deve `<CDATA[`essere racchiuso tra... [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per eseguire l'escape del [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]contenuto di, in modo che un processore (che interpreta lo schema o lo schema) non tenti di interpretare il contenuto letteralmente come. `]]>`  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>Limitazioni del codice inline  
 È consigliabile evitare o limitare l'utilizzo del codice inline. In termini di architettura e filosofia di codifica, mantenere una separazione tra markup e code-behind mantiene i ruoli di progettazione e sviluppo molto più distinti. A un livello più tecnico, il codice scritto per il codice inline può essere scomodo da scrivere, perché si sta scrivendo sempre nella [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] classe parziale generata e può utilizzare solo i mapping degli spazi dei nomi XML predefiniti. Poiché non è possibile `using` aggiungere istruzioni, è necessario qualificare in modo completo molte delle chiamate API effettuate. I mapping [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefiniti includono Gran parte, ma non tutti gli spazi dei nomi CLR presenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] negli assembly. sarà necessario qualificare completamente le chiamate a tipi e membri contenuti negli altri spazi dei nomi CLR. Non è inoltre possibile definire alcunché oltre la classe parziale nel codice inline e tutte le entità del codice utente a cui si fa riferimento devono esistere come membro o variabile all'interno della classe parziale generata. Anche altre funzionalità di programmazione specifiche del linguaggio, come `#ifdef` le macro o le variabili globali o le variabili di compilazione, non sono disponibili. Per altre informazioni, vedere [tipo XAML intrinseco x:code](../../xaml-services/x-code-intrinsic-xaml-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Tipo XAML intrinseco x:Code](../../xaml-services/x-code-intrinsic-xaml-type.md)
- [Compilazione di un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
