---
title: Direttive per il preprocessore C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "69608605"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="c0eb6-102">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="c0eb6-102">C# preprocessor directives</span></span>
<span data-ttu-id="c0eb6-103">Questa sezione contiene informazioni sulle seguenti direttive per il preprocessore C#:</span><span class="sxs-lookup"><span data-stu-id="c0eb6-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="c0eb6-104">#if</span><span class="sxs-lookup"><span data-stu-id="c0eb6-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="c0eb6-105">#else</span><span class="sxs-lookup"><span data-stu-id="c0eb6-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="c0eb6-106">#elif</span><span class="sxs-lookup"><span data-stu-id="c0eb6-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="c0eb6-107">#endif</span><span class="sxs-lookup"><span data-stu-id="c0eb6-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="c0eb6-108"># define</span><span class="sxs-lookup"><span data-stu-id="c0eb6-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="c0eb6-109">#undef</span><span class="sxs-lookup"><span data-stu-id="c0eb6-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="c0eb6-110">#warning</span><span class="sxs-lookup"><span data-stu-id="c0eb6-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="c0eb6-111">#error</span><span class="sxs-lookup"><span data-stu-id="c0eb6-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="c0eb6-112">#line</span><span class="sxs-lookup"><span data-stu-id="c0eb6-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="c0eb6-113">#region</span><span class="sxs-lookup"><span data-stu-id="c0eb6-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="c0eb6-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="c0eb6-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="c0eb6-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="c0eb6-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="c0eb6-116">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="c0eb6-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="c0eb6-117">Checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="c0eb6-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="c0eb6-118">Per altre informazioni ed esempi, vedere i singoli argomenti.</span><span class="sxs-lookup"><span data-stu-id="c0eb6-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="c0eb6-119">Anche se il compilatore non ha un preprocessore indipendente, le direttive descritte in questa sezione vengono elaborate come se ne esistesse uno.</span><span class="sxs-lookup"><span data-stu-id="c0eb6-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="c0eb6-120">Vengono usate come supporto nella compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="c0eb6-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="c0eb6-121">A differenza delle direttive di C e C++, non è possibile usare queste direttive per creare macro.</span><span class="sxs-lookup"><span data-stu-id="c0eb6-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="c0eb6-122">Una direttiva del preprocessore deve essere l'unica istruzione su una riga.</span><span class="sxs-lookup"><span data-stu-id="c0eb6-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0eb6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0eb6-123">See also</span></span>

- [<span data-ttu-id="c0eb6-124">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="c0eb6-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0eb6-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0eb6-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
