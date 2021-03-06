---
title: '#undef - Riferimenti per C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 21923412aa178c3b86e94a54bd911130e48e4deb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712442"
---
# <a name="undef-c-reference"></a>#undef (Riferimenti per C#)
`#undef` consente di rimuovere la definizione di un simbolo. In questo modo, se si usa il simbolo come espressione in una direttiva [#if](./preprocessor-if.md), l'espressione restituirà `false`.  
  
 Un simbolo può essere definito con la direttiva [#define](./preprocessor-define.md) o con l'opzione del compilatore [-define.](../compiler-options/define-compiler-option.md) È necessario che la direttiva `#undef` venga visualizzata in un file prima di usare istruzioni che non siano anche direttive.  
  
## <a name="example"></a>Esempio  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**DEBUG non è stato definito**

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore di C](./index.md)
