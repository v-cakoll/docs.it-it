---
title: '#elif (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1512bbbc46ce15570507c8b51540eef607d55dc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="elif-c-reference"></a>#elif (Riferimenti per C#)
`#elif` consente di creare una direttiva condizionale composita. L'espressione `#elif` viene valutata quando né l'espressione [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) che la precede, né eventuali espressioni delle direttive `#elif` facoltative che la precedono, restituiscono `true`. Se un'espressione `#elif` restituisce `true`, il compilatore valuterà tutto il codice compreso tra `#elif` e la direttiva condizionale successiva. Ad esempio:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 È possibile usare gli operatori `==` (uguaglianza), `!=` (disuguaglianza), `&&` (and), e `||` (or) per valutare più simboli. È anche possibile raggruppare simboli e operatori tra parentesi.  
  
## <a name="remarks"></a>Note  
 `#elif` equivale a usare:  
  
```csharp
#else  
#if  
```  
  
 L'utilizzo di `#elif` è più semplice perché ogni espressione `#if` richiede un'espressione [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mentre un'espressione `#elif` può essere usata anche senza un'espressione `#endif` corrispondente.  
  
 Per un esempio di utilizzo di `#elif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)
