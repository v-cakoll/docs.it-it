---
title: Confronto tra proprietà e indicizzatori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 330d222083ce599719698c023803196dfe88da84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712130"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Confronto tra proprietà e indicizzatori (Guida per programmatori C#)
Gli indicizzatori sono come proprietà. Ad eccezione delle differenze illustrate nella tabella seguente, tutte le regole definite per le funzioni di accesso a proprietà si applicano anche alle funzioni di accesso a indicizzatori.  
  
|Proprietà|Indexer|  
|--------------|-------------|  
|Consente di chiamare metodi come se fossero membri dati pubblici.|Consente di accedere agli elementi di una raccolta interna di un oggetto tramite la notazione di matrice per l'oggetto stesso.|  
|Accesso tramite nome semplice.|Accesso tramite indice.|  
|Può essere un membro statico o un membro di istanza.|Deve essere un membro di istanza.|  
|La funzione di accesso [get](../../language-reference/keywords/get.md) di una proprietà non ha parametri.|La funzione di accesso `get` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore.|  
|La funzione di accesso [set](../../language-reference/keywords/set.md) di una proprietà contiene il parametro `value` implicito.|La funzione di accesso `set` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore e anche il parametro [value](../../language-reference/keywords/value.md).|  
|Supporta la sintassi abbreviata con [proprietà implementate automaticamente](../classes-and-structs/auto-implemented-properties.md).|Supporta membri con corpo di espressione per ottenere solo indicizzatori.|  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Indicizzatori](./index.md)
- [Proprietà](../classes-and-structs/properties.md)
