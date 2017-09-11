---
title: '#<a name="undef-c-reference"></a>undef (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
dev_langs:
- CSharp
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
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
ms.openlocfilehash: acdd043535ef319f2af40c809e7fe4af612cb17d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="undef-c-reference"></a><span data-ttu-id="0bfdb-102">#undef (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0bfdb-102">#undef (C# Reference)</span></span>
<span data-ttu-id="0bfdb-103">`#undef` consente di rimuovere la definizione di un simbolo. In questo modo, se si usa il simbolo come espressione in una direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), l'espressione restituirà `false`.</span><span class="sxs-lookup"><span data-stu-id="0bfdb-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="0bfdb-104">Un simbolo può essere definito con la direttiva [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) o con l'opzione di compilazione [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0bfdb-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="0bfdb-105">È necessario che la direttiva `#undef` venga visualizzata in un file prima di usare istruzioni che non siano anche direttive.</span><span class="sxs-lookup"><span data-stu-id="0bfdb-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bfdb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bfdb-106">Example</span></span>  
  
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
  
 <span data-ttu-id="0bfdb-107">**DEBUG non è stato definito**</span><span class="sxs-lookup"><span data-stu-id="0bfdb-107">**DEBUG is not defined**</span></span>   
## <a name="see-also"></a><span data-ttu-id="0bfdb-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bfdb-108">See Also</span></span>  
 <span data-ttu-id="0bfdb-109">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bfdb-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0bfdb-110">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bfdb-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0bfdb-111">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="0bfdb-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

