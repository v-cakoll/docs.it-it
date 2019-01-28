---
title: '#warning - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 55768a354b2841021607ed40b4ef87b9767edcad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620318"
---
# <a name="warning-c-reference"></a><span data-ttu-id="0e498-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0e498-102">#warning (C# Reference)</span></span>
<span data-ttu-id="0e498-103">`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="0e498-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="0e498-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0e498-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e498-105">Note</span><span class="sxs-lookup"><span data-stu-id="0e498-105">Remarks</span></span>
 <span data-ttu-id="0e498-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="0e498-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="0e498-107">È possibile anche generare un errore definito dall'utente tramite [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="0e498-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e498-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e498-108">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="0e498-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e498-109">See also</span></span>

- [<span data-ttu-id="0e498-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0e498-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="0e498-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0e498-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0e498-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="0e498-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
