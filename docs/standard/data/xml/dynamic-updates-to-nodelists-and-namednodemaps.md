---
title: Aggiornamenti dinamici di NodeLists e NamedNodeMaps
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 58dfde94c2f37b0a09ee795b9df20296c9f86da6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710973"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Aggiornamenti dinamici di NodeLists e NamedNodeMaps
Poiché in **XmlNodeList** e **XmlNamedNodeMap** è contenuto un set di nodi e il documento XML è già stato caricato in memoria e sottoposto a modifiche, il W3C (World Wide Web Consortium) stabilisce che questi oggetti contenenti set di nodi debbano essere dinamici. Vale a dire che, se il documento sottostante cambia, anche i dati di questi due oggetti cambiano di conseguenza. Se quindi un **XmlNodeList** contiene tutti gli elementi figlio di un particolare elemento (ad esempio l'elemento X), si aggiunge un ulteriore elemento, l'elemento Q, al documento sotto l'elemento X. Nell'elenco **XmlNodeList** deve essere disponibile anche il nuovo elemento Q aggiunto alla raccolta. Lo stesso vale per il contrario. Se si aggiunge un nodo a **XmlNodeList**, il documento sottostante viene anch'esso aggiornato.  
  
## <a name="see-also"></a>Vedi anche

- [XML DOM (Document Object Model)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
