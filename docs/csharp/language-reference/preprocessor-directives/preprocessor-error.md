---
title: '#error (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 9ea4c24dcc3c0a4d39499bee5900cb9c6cc768c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="error-c-reference"></a>#error (Riferimenti per C#)
`#error` consente di generare un errore da una posizione specifica nel codice. Ad esempio:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Note  
 La direttiva `#error` viene generalmente usata nelle direttive condizionali.  
  
 È possibile anche generare un avviso definito dall'utente tramite [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).  
  
## <a name="example"></a>Esempio  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)
