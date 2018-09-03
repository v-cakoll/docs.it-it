---
title: '#pragma (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 5ae397cc61e0c6b58ed2079369131ebb7e352eae
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482935"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="2bbb0-102">#pragma (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2bbb0-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="2bbb0-103">`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="2bbb0-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="2bbb0-104">Le istruzioni devono essere supportate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="2bbb0-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="2bbb0-105">In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2bbb0-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="2bbb0-106">Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:</span><span class="sxs-lookup"><span data-stu-id="2bbb0-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="2bbb0-107">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="2bbb0-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="2bbb0-108">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="2bbb0-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="2bbb0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bbb0-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bbb0-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bbb0-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="2bbb0-111">Nome di un pragma riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2bbb0-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="2bbb0-112">Argomenti specifici del pragma.</span><span class="sxs-lookup"><span data-stu-id="2bbb0-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbb0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bbb0-113">See Also</span></span>

- [<span data-ttu-id="2bbb0-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2bbb0-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2bbb0-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2bbb0-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2bbb0-116">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="2bbb0-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="2bbb0-117">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="2bbb0-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="2bbb0-118">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="2bbb0-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
