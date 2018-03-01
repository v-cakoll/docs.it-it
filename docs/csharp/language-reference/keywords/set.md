---
title: set (Riferimenti per C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b810280724dcf608859bfa455947a75ce64b7abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="set-c-reference"></a>set (Riferimenti per C#)
La parola chiave `set` definisce un metodo *funzione di accesso* in una proprietà o indicizzatore che assegna un valore alla proprietà o all'elemento dell'indicizzatore. Per altre informazioni ed esempi, vedere [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), [Proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indicizzatori](../../../csharp/programming-guide/indexers/index.md).  
  
L'esempio seguente definisce le funzioni di accesso `get` e `set` per una proprietà denominata `Seconds`. Usa il campo privato denominato `_seconds` per portare in secondo piano il valore della proprietà.  
 
 [!code-csharp[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  

Spesso la funzione di accesso `set` è costituita da una singola istruzione che restituisce un valore, come nell'esempio precedente. A partire da C# 7, è possibile implementare la funzione di accesso `set` come membro con corpo di espressione. L'esempio seguente implementa entrambe le funzioni di accesso `get` e `set` come membri con corpo di espressione.

 [!code-csharp[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
    
Per i casi semplici in cui le funzioni di accesso `get` e `set` di una proprietà non eseguono operazioni diverse dall'impostazione o recupero di un valore in un campo sottostante, è possibile sfruttare il supporto del compilatore C# per le proprietà implementate automaticamente. L'esempio seguente implementa `Hours` come una proprietà implementata automaticamente. 
  
 [!code-csharp[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
    
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)
