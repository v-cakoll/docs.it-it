---
title: '#error - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: f18dbd007e80397b815256231a1d56e5ca50010e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608566"
---
# <a name="error-c-reference"></a><span data-ttu-id="e07a0-102">#error (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e07a0-102">#error (C# Reference)</span></span>
<span data-ttu-id="e07a0-103">`#error` consente di generare l'errore definito dall'utente [CS1029](../compiler-messages/cs1029.md) da una posizione specifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="e07a0-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="e07a0-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e07a0-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="e07a0-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e07a0-105">Remarks</span></span>  
 <span data-ttu-id="e07a0-106">La direttiva `#error` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="e07a0-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="e07a0-107">È possibile anche generare un avviso definito dall'utente tramite [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="e07a0-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e07a0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e07a0-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e07a0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e07a0-109">See also</span></span>

- [<span data-ttu-id="e07a0-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e07a0-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e07a0-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e07a0-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e07a0-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="e07a0-112">C# Preprocessor Directives</span></span>](./index.md)
