---
title: '#warning - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715065"
---
# <a name="warning-c-reference"></a>#warning (Riferimenti per C#)
`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice. Ad esempio:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Note
 La direttiva `#warning` viene generalmente usata nelle direttive condizionali. È possibile anche generare un errore definito dall'utente tramite [#error](./preprocessor-error.md).  
  
## <a name="example"></a>Esempio  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore C#](./index.md)
