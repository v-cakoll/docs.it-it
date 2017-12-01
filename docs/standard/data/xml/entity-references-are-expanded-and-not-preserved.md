---
title: "Riferimenti alle entità espansi e non conservati"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069d3b94a0269917400e75fdbe975ec39dcfdb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Riferimenti alle entità espansi e non conservati
Quando il riferimento all'entità viene espanso e sostituito dal testo che esso rappresenta, il **XmlEntityReference** nodo non è stato creato. Al contrario, la dichiarazione di entità viene analizzata e nodi creati dal contenuto della dichiarazione vengono copiati al posto del **XmlEntityReference**. Pertanto, nel `&publisher;` esempio, il `&publisher;` non viene salvata, ma viene invece un **XmlText** nodo viene creato.  
  
 ![struttura ad albero espansa](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Struttura ad albero per i riferimenti alle entità espansi  
  
 Le entità carattere, come `B` o `<`, non sono mantenute, ma vengono sempre espanse e rappresentate come nodi di tipo text.  
  
 Per mantenere **XmlEntityReference** nodi e i nodi figlio del riferimento all'entità collegata, impostare il **EntityHandling** flag **ExpandCharEntities**. In caso contrario, lasciare il **EntityHandling** flag il valore predefinito, ovvero **ExpandEntities**. In questo caso nel DOM non si osserveranno nodi dei riferimenti alle entità. I nodi saranno sostituiti da copie dei nodi figlio della dichiarazione di entità.  
  
 Una conseguenza della mancata conservazione dei riferimenti alle entità è che quando il documento viene salvato e passato a un'altra applicazione, l'applicazione ricevente non è in grado di rilevare che i nodi sono stati generati da un riferimento all'entità. Tuttavia, se i riferimenti alle entità vengono conservati, l'applicazione ricevente rileva un riferimento all'entità e legge i nodi figlio. È evidente che i nodi figlio rappresentano le informazioni presenti nella dichiarazione di entità. Se i riferimenti alle entità vengono conservati, ad esempio, il DOM possiede teoricamente la struttura seguente.  
  
 XmlElement: publisher  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Se i riferimenti alle entità vengono espansi nel DOM, come avviene in base al metodo predefinito, il tipo di struttura ad albero è il seguente:  
  
 XmlElement: publisher  
  
 XmlText: Microsoft Press  
  
 Si noti che il nodo di riferimento di entità è scomparso e l'applicazione ricevente non è possibile indicare che il **XmlText** nodo contenente "Microsoft Press" è stato creato da una dichiarazione di entità.  
  
 Se si utilizza un lettore che non è possibile risolvere le entità, il **carico** metodo genera un'eccezione quando viene rilevato un riferimento all'entità.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
