---
title: Creazione di nuovi riferimenti alle entità
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
ms.openlocfilehash: 8c81aae89bbe5979dffdc47a369349bd2b3f2df7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710986"
---
# <a name="creating-new-entity-references"></a>Creazione di nuovi riferimenti alle entità
Il metodo **CreateEntityReference** consente di creare un nuovo nodo **XmlEntityReference**. Il modello DOM XML cerca di vedere se il nome dell'entità a cui si fa riferimento è già stato dichiarato. In caso affermativo, i nodi figlio del nodo **XmlEntityReference** vengono copiati dal nodo della dichiarazione di entità. Se non vi è alcuna dichiarazione di entità corrispondente, viene associato un nodo di testo vuoto come unico figlio del nodo del riferimento all'entità. Poiché i nodi figlio del nodo **XmlEntityReference** sono copie di altri nodi, questi nodi figlio sono di sola lettura e non è possibile modificarli.  
  
 Dopo aver copiato i nodi, è probabile che vi sia uno spazio dei nomi nell'area di validità nel punto del riferimento all'entità. Tale spazio dei nomi incide sulla configurazione di qualsiasi nodo di elemento o di attributo generato.  
  
> [!NOTE]
> Il modello DOM aggiunge nodi figlio a **EntityReference** solo quando si inserisce il nodo **EntityReference** nel documento. I nodi **EntityReference** appena creati non hanno nodi figlio.  
  
 Anche se **XmlDataDocument** è una classe derivata di **XmlDocument**, **XmlDataDocument** non supporta la creazione di riferimenti alle entità, perché gli elementi figlio di **EntityReference** sono di sola lettura. I nodi figlio di un nodo **EntityReference** possono interessare più di un'area. In tal caso, la parte di riga associata all'area contenente una parte di **EntityReference** sarà di sola lettura.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
