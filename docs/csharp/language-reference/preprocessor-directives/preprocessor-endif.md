---
title: '#endif - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712546"
---
# <a name="endif-c-reference"></a>#endif (Riferimenti per C#)
`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](./preprocessor-if.md). Ad esempio,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Osservazioni  
 Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`. Per un esempio di utilizzo di `#endif`, vedere [#if](./preprocessor-if.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore di C](./index.md)
