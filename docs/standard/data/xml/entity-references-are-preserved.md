---
title: "Riferimenti alle entità conservati"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>Riferimenti alle entità conservati
Quando il riferimento all'entità non è espanso, ma conservato, l'oggetto modello DOM (Document XML) viene compilato un **XmlEntityReference** nodo quando viene rilevato un riferimento all'entità.  
  
 Usando il seguente codice XML,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 il modello DOM compila un **XmlEntityReference** nodo quando viene rilevato il `&publisher;` riferimento. Il **XmlEntityReference** contiene nodi figlio copiati dal contenuto della dichiarazione di entità. Esempio di codice precedente contiene il testo nella dichiarazione di entità, pertanto un **XmlText** nodo viene creato come nodo figlio del nodo di riferimento di entità.  
  
 ![Struttura per i riferimenti alle entità conservati](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Struttura ad albero per i riferimenti alle entità conservati  
  
 I nodi figlio del **XmlEntityReference** sono copie di tutti gli elementi figlio di nodi creati dal **XmlEntity** nodo quando è stata rilevata la dichiarazione di entità.  
  
> [!NOTE]
>  I nodi copiati dal **XmlEntity** non sono sempre copie esatte una volta posizionate sotto il nodo di riferimento di entità. Nell'ambito del nodo del riferimento all'entità possono essere presenti spazi dei nomi che incidono sulla configurazione finale dei nodi figlio.  
  
 Per impostazione predefinita, le entità generali quali `&abc;` vengono mantenuti e **XmlEntityReference** vengono sempre creati nodi.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
