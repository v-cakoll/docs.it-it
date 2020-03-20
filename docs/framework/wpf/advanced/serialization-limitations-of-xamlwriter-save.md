---
title: Limitazioni relative alla serializzazione di XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 96e917898320fb5d49f4e7dfc27daa7750af9d41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174368"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitazioni relative alla serializzazione di XamlWriter.Save
L'API <xref:System.Windows.Markup.XamlWriter.Save%2A> può essere utilizzata per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] serializzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] il contenuto di un'applicazione come file. Esistono tuttavia limitazioni considerevoli relative alla definizione precisa dell'oggetto della serializzazione. Queste limitazioni vengono esaminate in questo argomento, insieme ad alcune considerazioni generali.  

<a name="Run_Time__Not_Design_Time_Representation"></a>
## <a name="run-time-not-design-time-representation"></a>Rappresentazione della fase di esecuzione, non della fase di progettazione  
 La filosofia di base di ciò che viene serializzato da una chiamata a <xref:System.Windows.Markup.XamlWriter.Save%2A> è che il risultato sarà una rappresentazione dell'oggetto da serializzare, in fase di esecuzione. Molte proprietà della fase [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di progettazione del file originale potrebbero [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] essere già ottimizzate o perse nel momento <xref:System.Windows.Markup.XamlWriter.Save%2A> in cui l'oggetto viene caricato come oggetti in memoria e non vengono mantenute quando si chiama per la serializzazione. Il risultato della serializzazione è una rappresentazione efficace dell'albero logico dell'applicazione costruito, ma non necessariamente del file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che lo ha prodotto. Questi problemi rendono estremamente difficile <xref:System.Windows.Markup.XamlWriter.Save%2A> utilizzare la serializzazione come parte di un'area di progettazione estesa. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
<a name="Serialization_is_Self_Contained"></a>
## <a name="serialization-is-self-contained"></a>La serializzazione è autonoma  
 L'output serializzato di <xref:System.Windows.Markup.XamlWriter.Save%2A> è indipendente; tutto ciò che viene [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] serializzato è contenuto all'interno di una singola pagina, con un singolo elemento radice e nessun riferimento esterno diverso dagli URI. Ad esempio, se una pagina faceva riferimento a risorse dalle risorse dell'applicazione, queste appariranno come componenti della pagina serializzata.  
  
<a name="Extension_References_are_Dereferenced"></a>
## <a name="extension-references-are-dereferenced"></a>I riferimenti alle estensioni vengono dereferenziati  
 I riferimenti comuni agli oggetti realizzati in diversi formati di estensione di markup, ad esempio `StaticResource` o `Binding`, saranno dereferenziati durante il processo di serializzazione. Questi erano già dereferenziati nel momento in cui gli oggetti <xref:System.Windows.Markup.XamlWriter.Save%2A> in memoria sono [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] stati creati dal runtime dell'applicazione e la logica non rivisita l'originale per ripristinare tali riferimenti all'output serializzato. In questo modo, potenzialmente qualsiasi valore associato ai dati o proveniente dalla risorsa viene bloccato sull'ultimo valore usato dalla rappresentazione in fase di esecuzione, con possibilità solo limitate o indirette di distinguerlo da qualsiasi altro valore impostato localmente. Le immagini vengono inoltre serializzate come riferimenti a oggetti alle immagini esistenti nel progetto, anziché come riferimenti di origine originali, perdendo qualsiasi nome file o URI a cui si è fatto originariamente riferimento. Perfino le risorse dichiarate all'interno della stessa pagina sono serializzate nel punto in cui vengono referenziate, anziché essere conservate come chiave della raccolta di risorse.  
  
<a name="Event_Handling_is_Not_Preserved"></a>
## <a name="event-handling-is-not-preserved"></a>La gestione degli eventi non viene mantenuta  
 Quando i gestori eventi aggiunti tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono serializzati, non vengono mantenuti. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] senza code-behind (e senza il relativo meccanismo x:Code) non consente di serializzare la logica procedurale di runtime. Poiché la serializzazione è autonoma e limitata all'albero logico, non sono disponibili funzionalità per l'archiviazione dei gestori eventi. Di conseguenza, gli attributi dei gestori eventi, sia l'attributo stesso che il valore della stringa indicante il nome del gestore, vengono rimossi dall'output [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Scenari realistici per l'uso di XamlWriter.Save  
 Sebbene le limitazioni elencate di seguito siano piuttosto <xref:System.Windows.Markup.XamlWriter.Save%2A> sostanziali, esistono ancora diversi scenari appropriati per l'utilizzo per la serializzazione.  
  
- Output vettoriale o grafico: l'output dell'area sottoposta a rendering può essere usato per riprodurre lo stesso vettore o la stessa grafica se caricato nuovamente.  
  
- Documenti RTF o dinamici: il testo con tutta la formattazione e il contenimento degli elementi inclusi viene mantenuto nell'output. Questo può essere utile per i meccanismi che si avvicinano a una funzionalità degli Appunti.  
  
- Conservazione dei dati degli oggetti business: se sono stati archiviati dati in elementi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] personalizzati, ad esempio dati XML, purché gli oggetti business seguano regole di base, ad esempio fornire costruttori personalizzati e la conversione per i valori delle proprietà in base al riferimento, questi oggetti business possono essere perpetuati tramite la serializzazione.
