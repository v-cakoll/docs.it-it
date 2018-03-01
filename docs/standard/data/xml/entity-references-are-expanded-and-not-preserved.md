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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 00b997865c614756ea5fd9567ded3baa469f4c62
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Riferimenti alle entità espansi e non conservati
Quando il riferimento a un'entità viene espanso e sostituito dal testo che esso rappresenta, il nodo **XmlEntityReference** non viene creato. Invece, la dichiarazione di entità viene analizzata e i nodi creati dal contenuto della dichiarazione vengono copiati al posto di **XmlEntityReference**. Nell'esempio di `&publisher;`, `&publisher;` non viene quindi salvato, ma viene creato un nodo **XmlText**.  
  
 ![Struttura ad albero espansa](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Struttura ad albero per i riferimenti alle entità espansi  
  
 Le entità carattere, come `B` o `<`, non sono mantenute, ma vengono sempre espanse e rappresentate come nodi di tipo text.  
  
 Per conservare i nodi **XmlEntityReference** e i nodi figlio del riferimento all'entità associati a quest'ultima, impostare il flag **EntityHandling** su **ExpandCharEntities**. In caso contrario, lasciare il flag **EntityHandling** sull'impostazione predefinita, ovvero **ExpandEntities**. In questo caso nel DOM non si osserveranno nodi dei riferimenti alle entità. I nodi saranno sostituiti da copie dei nodi figlio della dichiarazione di entità.  
  
 Una conseguenza della mancata conservazione dei riferimenti alle entità è che quando il documento viene salvato e passato a un'altra applicazione, l'applicazione ricevente non è in grado di rilevare che i nodi sono stati generati da un riferimento all'entità. Tuttavia, se i riferimenti alle entità vengono conservati, l'applicazione ricevente rileva un riferimento all'entità e legge i nodi figlio. È evidente che i nodi figlio rappresentano le informazioni presenti nella dichiarazione di entità. Se i riferimenti alle entità vengono conservati, ad esempio, il DOM possiede teoricamente la struttura seguente.  
  
 XmlElement: publisher  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Se i riferimenti alle entità vengono espansi nel DOM, come avviene in base al metodo predefinito, il tipo di struttura ad albero è il seguente:  
  
 XmlElement: publisher  
  
 XmlText: Microsoft Press  
  
 Si noti che il nodo del riferimento all'entità è scomparso e che l'applicazione ricevente non riesce a rilevare che il nodo **XmlText** contenente "Microsoft Press" era stato creato da una dichiarazione di entità.  
  
 Se si usa un lettore che non riesce a risolvere le entità, il metodo **Load** genera un'eccezione quando incontra un riferimento all'entità.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
