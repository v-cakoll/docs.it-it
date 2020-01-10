---
title: '#pragma warning - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5620ea9e5f31c22e26bee95a450335bb179ced25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712468"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="86369-102">#pragma warning (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="86369-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="86369-103">`#pragma warning` consente di abilitare o disabilitare alcuni avvisi.</span><span class="sxs-lookup"><span data-stu-id="86369-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86369-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86369-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="86369-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86369-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="86369-106">Elenco separato da virgole di numeri di avviso.</span><span class="sxs-lookup"><span data-stu-id="86369-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="86369-107">Il prefisso "CS" è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86369-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="86369-108">Quando non viene specificato alcun numero di avviso, `disable` disabilita tutti gli avvisi e `restore` abilita tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="86369-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86369-109">Per trovare i numeri di avviso in Visual Studio, compilare il progetto e quindi cercare i numeri di avviso nella finestra **Output**.</span><span class="sxs-lookup"><span data-stu-id="86369-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86369-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="86369-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86369-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86369-111">See also</span></span>

- [<span data-ttu-id="86369-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="86369-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="86369-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="86369-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="86369-114">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="86369-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="86369-115">Errori del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="86369-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
