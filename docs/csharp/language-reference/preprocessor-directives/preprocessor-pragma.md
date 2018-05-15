---
title: '#pragma (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: a4829d5062474922d45a2f4f8e1cddf9023b6ad8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="pragma-c-reference"></a><span data-ttu-id="800ff-102">#pragma (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="800ff-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="800ff-103">`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="800ff-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="800ff-104">Le istruzioni devono essere supportate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="800ff-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="800ff-105">In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="800ff-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="800ff-106">Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:</span><span class="sxs-lookup"><span data-stu-id="800ff-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="800ff-107">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="800ff-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="800ff-108">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="800ff-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="800ff-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="800ff-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="800ff-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="800ff-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="800ff-111">Nome di un pragma riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="800ff-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="800ff-112">Argomenti specifici del pragma.</span><span class="sxs-lookup"><span data-stu-id="800ff-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800ff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="800ff-113">See Also</span></span>  
 [<span data-ttu-id="800ff-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="800ff-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="800ff-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="800ff-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="800ff-116">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="800ff-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="800ff-117">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="800ff-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [<span data-ttu-id="800ff-118">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="800ff-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
