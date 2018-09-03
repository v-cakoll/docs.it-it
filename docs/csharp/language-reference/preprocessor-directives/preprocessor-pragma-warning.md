---
title: '#pragma warning (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 89ff8151d55ac58a1b114f7727297704ce26b9a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481930"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="3d925-102">#pragma warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3d925-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="3d925-103">`#pragma warning` consente di abilitare o disabilitare alcuni avvisi.</span><span class="sxs-lookup"><span data-stu-id="3d925-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d925-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d925-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d925-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d925-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="3d925-106">Elenco separato da virgole di numeri di avviso.</span><span class="sxs-lookup"><span data-stu-id="3d925-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="3d925-107">Il prefisso "CS" è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3d925-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="3d925-108">Quando non viene specificato alcun numero di avviso, `disable` disabilita tutti gli avvisi e `restore` abilita tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="3d925-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d925-109">Per trovare i numeri di avviso in Visual Studio, compilare il progetto e quindi cercare i numeri di avviso nella finestra **Output**.</span><span class="sxs-lookup"><span data-stu-id="3d925-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d925-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d925-110">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d925-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d925-111">See Also</span></span>

- [<span data-ttu-id="3d925-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3d925-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3d925-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3d925-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3d925-114">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="3d925-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="3d925-115">Errori del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="3d925-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
