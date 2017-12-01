---
title: "Creazione di nuovi riferimenti alle entità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>Creazione di nuovi riferimenti alle entità
Il **CreateEntityReference** crea un nuovo metodo **XmlEntityReference** nodo. Il modello DOM XML cerca di vedere se il nome dell'entità a cui si fa riferimento è già stato dichiarato. In caso affermativo, i nodi figlio del **XmlEntityReference** nodo vengono copiati dal nodo della dichiarazione di entità. Se non vi è alcuna dichiarazione di entità corrispondente, viene associato un nodo di testo vuoto come unico figlio del nodo del riferimento all'entità. Poiché i nodi figlio del **XmlEntityReference** nodo sono copie di altri nodi, questi nodi figlio sono di sola lettura e non possono essere modificati.  
  
 Dopo aver copiato i nodi, è probabile che vi sia uno spazio dei nomi nell'area di validità nel punto del riferimento all'entità. Tale spazio dei nomi incide sulla configurazione di qualsiasi nodo di elemento o di attributo generato.  
  
> [!NOTE]
>  Il DOM aggiunge i nodi figlio per il **EntityReference** solo quando si inserisce il **EntityReference** nodo nel documento. Appena creato **EntityReference** nodi non hanno nodi figlio.  
  
 Anche se il **XmlDataDocument** è una classe derivata del **XmlDocument**, **XmlDataDocument** non supporta la creazione di riferimenti a entità. In questo modo **EntityReference** gli elementi figlio sono di sola lettura. Gli elementi figlio di un **EntityReference** nodo può estendersi su più aree. In questo caso, parte di una riga associata con l'area che contiene una parte di un **EntityReference** sarà di sola lettura.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
