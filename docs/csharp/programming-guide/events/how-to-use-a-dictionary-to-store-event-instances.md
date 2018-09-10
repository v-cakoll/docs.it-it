---
title: 'Procedura: utilizzare un dizionario per archiviare istanze di evento (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: c3a804ce1bf1f5ac8db47f0f0c1f37d1ca5f781b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213173"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procedura: utilizzare un dizionario per archiviare istanze di evento (Guida per programmatori C#)
È possibile usare `accessor-declarations` per esporre numerosi eventi senza allocare un campo per ogni evento, ma usando invece un dizionario per archiviare le istanze degli eventi. Ciò è utile solo se si hanno molti eventi, ma si prevede che la maggior parte di essi non verrà implementata.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Eventi](../../../csharp/programming-guide/events/index.md)  
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
