---
title: '#warning - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 08fcefd904ad43c781017087082592120e21f5cd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236830"
---
# <a name="warning-c-reference"></a><span data-ttu-id="4ea70-102">#warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4ea70-102">#warning (C# Reference)</span></span>
<span data-ttu-id="4ea70-103">`#warning` consente di generare l'avviso [CS1030](../../misc/cs1030.md) di livello uno del compilatore da una posizione specifica del codice.</span><span class="sxs-lookup"><span data-stu-id="4ea70-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="4ea70-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4ea70-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ea70-105">Note</span><span class="sxs-lookup"><span data-stu-id="4ea70-105">Remarks</span></span>
 <span data-ttu-id="4ea70-106">La direttiva `#warning` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="4ea70-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="4ea70-107">È possibile anche generare un errore definito dall'utente tramite [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="4ea70-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ea70-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ea70-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="4ea70-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea70-109">See Also</span></span>

- [<span data-ttu-id="4ea70-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4ea70-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4ea70-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4ea70-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4ea70-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="4ea70-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
