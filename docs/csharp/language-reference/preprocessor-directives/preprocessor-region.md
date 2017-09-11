---
title: '#<a name="region-c-reference"></a>region (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
dev_langs:
- CSharp
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
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
ms.openlocfilehash: f7685d23bc1d40a0d0b6c9ac9a644019e1186eb7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="region-c-reference"></a><span data-ttu-id="b1832-102">#region (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b1832-102">#region (C# Reference)</span></span>
<span data-ttu-id="b1832-103">`#region` consente di specificare un blocco di codice che è possibile espandere o comprimere quando viene usata la funzionalità [Struttura](/visualstudio/ide/outlining) dell'editor di codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1832-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="b1832-104">Nei file di codice più lunghi, è consigliabile essere in grado di comprimere o nascondere una o più aree in modo da potersi concentrare sulla parte del file su cui si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="b1832-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="b1832-105">L'esempio seguente illustra come definire un'area:</span><span class="sxs-lookup"><span data-stu-id="b1832-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="b1832-106">Note</span><span class="sxs-lookup"><span data-stu-id="b1832-106">Remarks</span></span>  
 <span data-ttu-id="b1832-107">Un blocco `#region` deve terminare con la direttiva [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="b1832-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="b1832-108">Non è possibile sovrapporre un blocco `#region` con un blocco [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="b1832-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="b1832-109">È tuttavia possibile annidare un blocco `#region` in un blocco `#if` e un blocco `#if` in un blocco `#region`.</span><span class="sxs-lookup"><span data-stu-id="b1832-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1832-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1832-110">See Also</span></span>  
 <span data-ttu-id="b1832-111">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1832-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b1832-112">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1832-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b1832-113">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="b1832-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

