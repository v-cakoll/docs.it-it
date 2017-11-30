---
title: Aggiornamenti dinamici di NodeLists e NamedNodeMaps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Aggiornamenti dinamici di NodeLists e NamedNodeMaps
Poiché il **XmlNodeList** e **XmlNamedNodeMap** contengono un set di nodi, ma il documento XML viene caricato in memoria e viene modificato, il World Wide Web Consortium (W3C) indica che questi oggetti che contengono set di nodi devono essere dinamici. Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza. Pertanto, se dispone di un **XmlNodeList** che contiene tutti gli elementi figlio di un particolare elemento (ad esempio, l'elemento X), quindi aggiungere un ulteriore elemento, elemento Q, al documento sotto l'elemento X. Il **XmlNodeList** deve essere il nuovo elemento Q aggiunto alla relativa raccolta. Lo stesso vale per il contrario. Se viene aggiunto un nodo di **XmlNodeList**, il documento sottostante viene aggiornato automaticamente anche.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
