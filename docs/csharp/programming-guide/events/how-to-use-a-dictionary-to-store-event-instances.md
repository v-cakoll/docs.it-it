---
title: 'Procedura: Usare un dizionario per archiviare istanze di evento - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245142"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procedura: Usare un dizionario per archiviare istanze di evento (Guida per programmatori C#)
È possibile usare `accessor-declarations` per esporre numerosi eventi senza allocare un campo per ogni evento, ma usando invece un dizionario per archiviare le istanze degli eventi. Ciò è utile solo se si hanno molti eventi, ma si prevede che la maggior parte di essi non verrà implementata.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Eventi](../../../csharp/programming-guide/events/index.md)  
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
