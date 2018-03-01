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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Aggiornamenti dinamici di NodeLists e NamedNodeMaps
Poiché in **XmlNodeList** e **XmlNamedNodeMap** è contenuto un set di nodi e il documento XML è già stato caricato in memoria e sottoposto a modifiche, il W3C (World Wide Web Consortium) stabilisce che questi oggetti contenenti set di nodi debbano essere dinamici. Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza. Se quindi un **XmlNodeList** contiene tutti gli elementi figlio di un particolare elemento (ad esempio l'elemento X), si aggiunge un ulteriore elemento, l'elemento Q, al documento sotto l'elemento X. Nell'elenco **XmlNodeList** deve essere disponibile anche il nuovo elemento Q aggiunto alla raccolta. Lo stesso vale per il contrario. Se si aggiunge un nodo a **XmlNodeList**, il documento sottostante viene anch'esso aggiornato.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
