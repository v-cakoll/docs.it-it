---
title: '#define - Riferimenti per C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: c08d6f42c11184a4d14aa6712f9f0f8706a72cab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173432"
---
# <a name="define-c-reference"></a><span data-ttu-id="3f3fe-102">#define (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3f3fe-102">#define (C# Reference)</span></span>
<span data-ttu-id="3f3fe-103">Si usa `#define` per definire un simbolo.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="3f3fe-104">Quando si usa il simbolo come espressione passata alla direttiva [#if](./preprocessor-if.md), l'espressione restituisce `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3f3fe-104">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="3f3fe-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3f3fe-105">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f3fe-106">Non è possibile usare la direttiva `#define` per dichiarare valori costanti come in C e in C++.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="3f3fe-107">Le costanti in C# possono essere definite come membri statici di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="3f3fe-108">Se sono presenti più costanti di questo tipo, per usarle può essere utile creare una classe di costanti separata.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="3f3fe-109">Per specificare le condizioni per la compilazione è possibile usare simboli.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="3f3fe-110">È possibile eseguire il test del simbolo tramite [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="3f3fe-110">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="3f3fe-111">È anche possibile usare <xref:System.Diagnostics.ConditionalAttribute> per eseguire una compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-111">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="3f3fe-112">È possibile definire un simbolo ma non è possibile assegnare a questo un valore.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="3f3fe-113">La direttiva `#define` deve essere inserita in un file prima di usare istruzioni che non siano anche direttive del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="3f3fe-114">È anche possibile definire un simbolo con l'opzione del compilatore [-define.](../compiler-options/define-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="3f3fe-114">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="3f3fe-115">Per rimuovere la definizione di un simbolo, è possibile usare [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="3f3fe-115">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="3f3fe-116">Un simbolo definito tramite `-define` o `#define` non provoca conflitti con una variabile avente lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="3f3fe-117">Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="3f3fe-118">L'ambito di un simbolo creato tramite `#define` è il file in cui il simbolo è stato definito.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="3f3fe-119">Come illustrato nell'esempio seguente, è necessario inserire direttive `#define` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="3f3fe-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="3f3fe-120">Per un esempio su come annullare la definizione di un simbolo, vedere [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="3f3fe-120">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3fe-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f3fe-121">See also</span></span>

- [<span data-ttu-id="3f3fe-122">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="3f3fe-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3f3fe-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3f3fe-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3f3fe-124">Direttive per il preprocessore di C</span><span class="sxs-lookup"><span data-stu-id="3f3fe-124">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="3f3fe-125">const</span><span class="sxs-lookup"><span data-stu-id="3f3fe-125">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="3f3fe-126">Procedura: compilare in modo condizionale con traccia e debug</span><span class="sxs-lookup"><span data-stu-id="3f3fe-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="3f3fe-127">#undef</span><span class="sxs-lookup"><span data-stu-id="3f3fe-127">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="3f3fe-128">#if</span><span class="sxs-lookup"><span data-stu-id="3f3fe-128">#if</span></span>](./preprocessor-if.md)
