---
title: '#error - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 7203e1271da66e78bfbd70717b0f5e536a7ebd86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712520"
---
# <a name="error-c-reference"></a><span data-ttu-id="dfa0d-102">#error (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dfa0d-102">#error (C# Reference)</span></span>
<span data-ttu-id="dfa0d-103">`#error` consente di generare l'errore definito dall'utente [CS1029](../compiler-messages/cs1029.md) da una posizione specifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="dfa0d-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="dfa0d-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dfa0d-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="dfa0d-105">Note</span><span class="sxs-lookup"><span data-stu-id="dfa0d-105">Remarks</span></span>  
 <span data-ttu-id="dfa0d-106">La direttiva `#error` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="dfa0d-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="dfa0d-107">È possibile anche generare un avviso definito dall'utente tramite [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="dfa0d-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfa0d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfa0d-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfa0d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfa0d-109">See also</span></span>

- [<span data-ttu-id="dfa0d-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="dfa0d-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dfa0d-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="dfa0d-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dfa0d-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="dfa0d-112">C# Preprocessor Directives</span></span>](./index.md)
