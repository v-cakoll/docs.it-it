---
title: '#pragma - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712455"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="0b804-102">#pragma (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0b804-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="0b804-103">`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="0b804-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="0b804-104">Le istruzioni devono essere supportate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b804-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="0b804-105">In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0b804-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="0b804-106">Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b804-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="0b804-107">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="0b804-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="0b804-108">Checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="0b804-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="0b804-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b804-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b804-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b804-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="0b804-111">Nome di un pragma riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0b804-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="0b804-112">Argomenti specifici del pragma.</span><span class="sxs-lookup"><span data-stu-id="0b804-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b804-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b804-113">See also</span></span>

- [<span data-ttu-id="0b804-114">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="0b804-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0b804-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0b804-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0b804-116">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="0b804-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="0b804-117">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="0b804-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="0b804-118">Checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="0b804-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
