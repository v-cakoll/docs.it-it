---
title: Come combinare i delegati (delegati multicast) - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705379"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>Come combinare delegati (delegati multicast) (Guida per programmatori C#)
Questo esempio illustra come creare delegati multicast. Una proprietà utile degli oggetti [delegate](../../language-reference/builtin-types/reference-types.md) è la possibilità di assegnare più oggetti a un'istanza di delegato usando l'operatore `+`. Il delegato multicast contiene un elenco dei delegati assegnati. Quando il delegato multicast viene chiamato, richiama i delegati nell'elenco, in ordine. Solo i delegati dello stesso tipo possono essere combinati.  
  
 L'operatore `-` può essere usato per rimuovere un delegato componente da un delegato multicast.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.MulticastDelegate>
- [Guida per programmatori C#](../index.md)
- [Events](../events/index.md)
