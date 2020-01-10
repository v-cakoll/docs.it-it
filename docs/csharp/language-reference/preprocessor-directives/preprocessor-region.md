---
title: '#region - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 723a904d18955caceea9e0d485ab51f84366c66e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715123"
---
# <a name="region-c-reference"></a><span data-ttu-id="a827c-102">#region (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a827c-102">#region (C# Reference)</span></span>
<span data-ttu-id="a827c-103">`#region` consente di specificare un blocco di codice che è possibile espandere o comprimere quando viene usata la funzionalità [Struttura](/visualstudio/ide/outlining) dell'editor di codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a827c-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="a827c-104">Nei file di codice più lunghi, è consigliabile essere in grado di comprimere o nascondere una o più aree in modo da potersi concentrare sulla parte del file su cui si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="a827c-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="a827c-105">L'esempio seguente illustra come definire un'area:</span><span class="sxs-lookup"><span data-stu-id="a827c-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="a827c-106">Note</span><span class="sxs-lookup"><span data-stu-id="a827c-106">Remarks</span></span>  
 <span data-ttu-id="a827c-107">Un blocco `#region` deve terminare con la direttiva [#endregion](./preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="a827c-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="a827c-108">Non è possibile sovrapporre un blocco `#region` con un blocco [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="a827c-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="a827c-109">È tuttavia possibile annidare un blocco `#region` in un blocco `#if` e un blocco `#if` in un blocco `#region`.</span><span class="sxs-lookup"><span data-stu-id="a827c-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a827c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a827c-110">See also</span></span>

- [<span data-ttu-id="a827c-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a827c-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a827c-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a827c-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a827c-113">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="a827c-113">C# Preprocessor Directives</span></span>](./index.md)
