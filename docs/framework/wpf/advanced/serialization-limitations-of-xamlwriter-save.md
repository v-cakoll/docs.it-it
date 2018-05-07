---
title: Limitazioni relative alla serializzazione di XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: cbe8d517b8794f6aae7190457a077422d235acb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitazioni relative alla serializzazione di XamlWriter.Save
Il [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> può essere utilizzato per serializzare il contenuto di un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazione come un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file. Esistono tuttavia limitazioni considerevoli relative alla definizione precisa dell'oggetto della serializzazione. Queste limitazioni vengono esaminate in questo argomento, insieme ad alcune considerazioni generali.  
  
 
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Rappresentazione della fase di esecuzione, non della fase di progettazione  
 La scelta degli elementi da serializzare tramite una chiamata a <xref:System.Windows.Markup.XamlWriter.Save%2A> è che il risultato sarà una rappresentazione dell'oggetto serializzato, in fase di esecuzione. Molte proprietà in fase di progettazione dell'originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file potrebbe già essere ottimizzato o perse al momento che il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene caricato come oggetti in memoria e non vengono mantenute quando si chiama <xref:System.Windows.Markup.XamlWriter.Save%2A> da serializzare. Il risultato della serializzazione è una rappresentazione efficace dell'albero logico dell'applicazione costruito, ma non necessariamente del file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che lo ha prodotto. Questi problemi rendono estremamente difficile l'utilizzo di <xref:System.Windows.Markup.XamlWriter.Save%2A> serializzazione come parte di un vasto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] area di progettazione.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>La serializzazione è autonoma  
 Output della serializzazione di <xref:System.Windows.Markup.XamlWriter.Save%2A> autonomo; tutto ciò che viene serializzato è contenuto all'interno di un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] singola pagina, con un singolo elemento radice e non i riferimenti esterni diverso da [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Ad esempio, se una pagina faceva riferimento a risorse dalle risorse dell'applicazione, queste appariranno come componenti della pagina serializzata.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>I riferimenti alle estensioni vengono dereferenziati  
 I riferimenti comuni agli oggetti realizzati in diversi formati di estensione di markup, ad esempio `StaticResource` o `Binding`, saranno dereferenziati durante il processo di serializzazione. Questi sono stati già dereferenziati nel momento in cui gli oggetti in memoria sono stati creati dal runtime di applicazione, e <xref:System.Windows.Markup.XamlWriter.Save%2A> logica prevede originale [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per ripristinare tali riferimenti nell'output serializzato. In questo modo, potenzialmente qualsiasi valore associato ai dati o proveniente dalla risorsa viene bloccato sull'ultimo valore usato dalla rappresentazione in fase di esecuzione, con possibilità solo limitate o indirette di distinguerlo da qualsiasi altro valore impostato localmente. Anche le immagini vengono serializzate come riferimenti a oggetti in base alle immagini esistenti nel progetto, anziché come riferimenti all'origine effettiva, con la conseguente perdita di qualsiasi nome file o [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] referenziato in origine. Perfino le risorse dichiarate all'interno della stessa pagina sono serializzate nel punto in cui vengono referenziate, anziché essere conservate come chiave della raccolta di risorse.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>La gestione degli eventi non viene mantenuta  
 Quando i gestori eventi aggiunti tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono serializzati, non vengono mantenuti. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] senza code-behind (e senza il relativo meccanismo x:Code) non consente di serializzare la logica procedurale di runtime. Poiché la serializzazione è autonoma e limitata all'albero logico, non sono disponibili funzionalità per l'archiviazione dei gestori eventi. Di conseguenza, gli attributi dei gestori eventi, sia l'attributo stesso che il valore della stringa indicante il nome del gestore, vengono rimossi dall'output [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Scenari realistici per l'uso di XamlWriter.Save  
 Mentre le limitazioni elencate di seguito sono piuttosto rilevanti, esistono diversi scenari appropriati per l'utilizzo di <xref:System.Windows.Markup.XamlWriter.Save%2A> per la serializzazione.  
  
-   Output vettoriale o grafico: l'output dell'area sottoposta a rendering può essere usato per riprodurre lo stesso vettore o la stessa grafica se caricato nuovamente.  
  
-   Documenti RTF o dinamici: il testo con tutta la formattazione e il contenimento degli elementi inclusi viene mantenuto nell'output. Questo può essere utile per i meccanismi che si avvicinano a una funzionalità degli Appunti.  
  
-   Conservazione dei dati di oggetti business: se in elementi personalizzati sono stati archiviati dei dati, ad esempio dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], finché gli oggetti business seguono le regole [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di base, ad esempio fornire costruttori personalizzati e la conversione per valori di proprietà per riferimento, è possibile conservare tali oggetti business con la serializzazione.
