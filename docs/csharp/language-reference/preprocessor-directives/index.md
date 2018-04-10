---
title: Direttive per il preprocessore C#
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6378c8df794a4ee75e7b5ca283b18b228ba46383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="87333-102">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="87333-102">C# preprocessor directives</span></span>
<span data-ttu-id="87333-103">Questa sezione contiene informazioni sulle seguenti direttive per il preprocessore C#:</span><span class="sxs-lookup"><span data-stu-id="87333-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="87333-104">#if</span><span class="sxs-lookup"><span data-stu-id="87333-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="87333-105">#else</span><span class="sxs-lookup"><span data-stu-id="87333-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="87333-106">#elif</span><span class="sxs-lookup"><span data-stu-id="87333-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="87333-107">#endif</span><span class="sxs-lookup"><span data-stu-id="87333-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="87333-108">#define</span><span class="sxs-lookup"><span data-stu-id="87333-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="87333-109">#undef</span><span class="sxs-lookup"><span data-stu-id="87333-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="87333-110">#warning</span><span class="sxs-lookup"><span data-stu-id="87333-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="87333-111">#error</span><span class="sxs-lookup"><span data-stu-id="87333-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="87333-112">#line</span><span class="sxs-lookup"><span data-stu-id="87333-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="87333-113">#region</span><span class="sxs-lookup"><span data-stu-id="87333-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="87333-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="87333-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="87333-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="87333-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="87333-116">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="87333-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="87333-117">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="87333-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="87333-118">Per altre informazioni ed esempi, vedere i singoli argomenti.</span><span class="sxs-lookup"><span data-stu-id="87333-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="87333-119">Anche se il compilatore non ha un preprocessore indipendente, le direttive descritte in questa sezione vengono elaborate come se ne esistesse uno.</span><span class="sxs-lookup"><span data-stu-id="87333-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="87333-120">Vengono usate come supporto nella compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="87333-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="87333-121">A differenza delle direttive di C e C++, non è possibile usare queste direttive per creare macro.</span><span class="sxs-lookup"><span data-stu-id="87333-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="87333-122">Una direttiva del preprocessore deve essere l'unica istruzione su una riga.</span><span class="sxs-lookup"><span data-stu-id="87333-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="87333-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87333-123">See also</span></span>
 [<span data-ttu-id="87333-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="87333-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="87333-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="87333-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
