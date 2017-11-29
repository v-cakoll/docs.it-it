---
title: "Confronto tra proprietà e indicizzatori (Guida per programmatori C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 102a6a97726fa19fcba0e6f19876a3935e8625f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Confronto tra proprietà e indicizzatori (Guida per programmatori C#)
Gli indicizzatori sono come proprietà. Ad eccezione delle differenze illustrate nella tabella seguente, tutte le regole definite per le funzioni di accesso a proprietà si applicano anche alle funzioni di accesso a indicizzatori.  
  
|Proprietà|Indicizzatore|  
|--------------|-------------|  
|Consente di chiamare metodi come se fossero membri dati pubblici.|Consente di accedere agli elementi di una raccolta interna di un oggetto tramite la notazione di matrice per l'oggetto stesso.|  
|Accesso tramite nome semplice.|Accesso tramite indice.|  
|Può essere un membro statico o un membro di istanza.|Deve essere un membro di istanza.|  
|La funzione di accesso [get](../../../csharp/language-reference/keywords/get.md) di una proprietà non ha parametri.|La funzione di accesso `get` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore.|  
|La funzione di accesso [set](../../../csharp/language-reference/keywords/set.md) di una proprietà contiene il parametro `value` implicito.|La funzione di accesso `set` di un indicizzatore ha lo stesso elenco di parametri formali dell'indicizzatore e anche il parametro [value](../../../csharp/language-reference/keywords/value.md).|  
|Supporta la sintassi abbreviata con [proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Non supporta la sintassi abbreviata.|  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)
