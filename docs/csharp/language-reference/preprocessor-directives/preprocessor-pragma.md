---
title: '#<a name="pragma-c-reference"></a>pragma (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
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
ms.openlocfilehash: e03fc387b105c1dee3b7fed93263ad8ef22d5934
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-c-reference"></a><span data-ttu-id="0fd80-102">#pragma (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0fd80-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="0fd80-103">`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="0fd80-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="0fd80-104">Le istruzioni devono essere supportate dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0fd80-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="0fd80-105">In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0fd80-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="0fd80-106">Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fd80-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="0fd80-107">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="0fd80-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="0fd80-108">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="0fd80-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="0fd80-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fd80-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fd80-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fd80-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="0fd80-111">Nome di un pragma riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0fd80-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="0fd80-112">Argomenti specifici del pragma.</span><span class="sxs-lookup"><span data-stu-id="0fd80-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd80-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fd80-113">See Also</span></span>  
 <span data-ttu-id="0fd80-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fd80-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0fd80-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fd80-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0fd80-116">[Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fd80-116">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="0fd80-117">[avviso #pragma](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span><span class="sxs-lookup"><span data-stu-id="0fd80-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span></span>  
 [<span data-ttu-id="0fd80-118">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="0fd80-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

