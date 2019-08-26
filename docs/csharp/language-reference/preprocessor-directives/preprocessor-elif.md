---
title: '#elif - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: b04db4bd23a459043efec59b8ebf9d322defbcf7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608591"
---
# <a name="elif-c-reference"></a>#elif (Riferimenti per C#)
`#elif` consente di creare una direttiva condizionale composita. L'espressione `#elif` viene valutata quando né l'espressione [#if](./preprocessor-if.md) che la precede, né eventuali espressioni delle direttive `#elif` facoltative che la precedono, restituiscono `true`. Se un'espressione `#elif` restituisce `true`, il compilatore valuterà tutto il codice compreso tra `#elif` e la direttiva condizionale successiva. Ad esempio:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 È possibile usare gli operatori `==` (uguaglianza), `!=` (disuguaglianza), `&&` (and), e `||` (or) per valutare più simboli. È anche possibile raggruppare simboli e operatori tra parentesi.  
  
## <a name="remarks"></a>Osservazioni  
 `#elif` equivale a usare:  
  
```csharp
#else  
#if  
```  
  
 L'utilizzo di `#elif` è più semplice perché ogni espressione `#if` richiede un'espressione [#endif](./preprocessor-endif.md), mentre un'espressione `#elif` può essere usata anche senza un'espressione `#endif` corrispondente.  
  
 Per un esempio di utilizzo di `#elif`, vedere [#if](./preprocessor-if.md).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore C#](./index.md)
