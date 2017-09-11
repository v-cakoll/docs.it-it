---
title: '#<a name="error-c-reference"></a>error (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
dev_langs:
- CSharp
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2d497d7b8345b94dfc77176bf2b0ca79674e9be
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="error-c-reference"></a><span data-ttu-id="229bd-102">#error (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="229bd-102">#error (C# Reference)</span></span>
<span data-ttu-id="229bd-103">`#error` consente di generare un errore da una posizione specifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="229bd-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="229bd-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="229bd-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="229bd-105">Note</span><span class="sxs-lookup"><span data-stu-id="229bd-105">Remarks</span></span>  
 <span data-ttu-id="229bd-106">La direttiva `#error` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="229bd-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="229bd-107">È possibile anche generare un avviso definito dall'utente tramite [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="229bd-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="229bd-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="229bd-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="229bd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="229bd-109">See Also</span></span>  
 <span data-ttu-id="229bd-110">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="229bd-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="229bd-111">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="229bd-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="229bd-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="229bd-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

