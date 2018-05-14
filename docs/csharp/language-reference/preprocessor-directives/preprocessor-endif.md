---
title: '#endif (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 1686e706ce5cae3b2eaa28a7e1c89b5694b2be88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="endif-c-reference"></a>#endif (Riferimenti per C#)
`#endif` specifica la fine di una direttiva condizionale iniziata con la direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Ad esempio,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Note  
 Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`. Per un esempio di utilizzo di `#endif`, vedere [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)
