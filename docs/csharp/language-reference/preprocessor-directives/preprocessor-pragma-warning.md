---
title: '#<a name="pragma-warning-c-reference"></a>pragma warning (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75c11acfd096d36c96ceb9e9c5c0d16e47e58fa1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-warning-c-reference"></a>#pragma warning (Riferimenti per C#)
`#pragma warning` consente di abilitare o disabilitare alcuni avvisi.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a>Parametri  
 `warning-list`  
 Elenco separato da virgole di numeri di avviso. Il prefisso "CS" è facoltativo.  
  
 Quando non viene specificato alcun numero di avviso, `disable` disabilita tutti gli avvisi e `restore` abilita tutti gli avvisi.  
  
> [!NOTE]
>  Per trovare i numeri di avviso in Visual Studio, compilare il progetto e quindi cercare i numeri di avviso nella finestra **Output**.  
  
## <a name="example"></a>Esempio  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [Errori del compilatore C#](../../../csharp/language-reference/compiler-messages/index.md)

