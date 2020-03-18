---
title: '#pragma warning - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5620ea9e5f31c22e26bee95a450335bb179ced25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712468"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="11135-102">#pragma warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="11135-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="11135-103">`#pragma warning` consente di abilitare o disabilitare alcuni avvisi.</span><span class="sxs-lookup"><span data-stu-id="11135-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11135-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11135-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="11135-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11135-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="11135-106">Elenco separato da virgole di numeri di avviso.</span><span class="sxs-lookup"><span data-stu-id="11135-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="11135-107">Il prefisso "CS" è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="11135-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="11135-108">Quando non viene specificato alcun numero di avviso, `disable` disabilita tutti gli avvisi e `restore` abilita tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="11135-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11135-109">Per trovare i numeri di avviso in Visual Studio, compilare il progetto e quindi cercare i numeri di avviso nella finestra **Output**.</span><span class="sxs-lookup"><span data-stu-id="11135-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11135-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="11135-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11135-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11135-111">See also</span></span>

- [<span data-ttu-id="11135-112">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="11135-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="11135-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="11135-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="11135-114">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="11135-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="11135-115">Errori del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="11135-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
