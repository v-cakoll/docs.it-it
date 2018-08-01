---
title: '#define (Riferimenti per C#)'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: f40c32a89641256e4f8fe30cd24f523b898139d5
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143479"
---
# <a name="define-c-reference"></a><span data-ttu-id="2ac8f-102">#define (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2ac8f-102">#define (C# Reference)</span></span>
<span data-ttu-id="2ac8f-103">Si usa `#define` per definire un simbolo.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="2ac8f-104">Quando si usa il simbolo come espressione passata alla direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), l'espressione restituisce `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2ac8f-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="2ac8f-105">Note</span><span class="sxs-lookup"><span data-stu-id="2ac8f-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac8f-106">Non è possibile usare la direttiva `#define` per dichiarare valori costanti come in C e in C++.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="2ac8f-107">Le costanti in C# possono essere definite come membri statici di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="2ac8f-108">Se sono presenti più costanti di questo tipo, per usarle può essere utile creare una classe di costanti separata.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="2ac8f-109">Per specificare le condizioni per la compilazione è possibile usare simboli.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="2ac8f-110">È possibile eseguire il test del simbolo tramite [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="2ac8f-110">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="2ac8f-111">È anche possibile usare l'attributo `conditional` per eseguire una compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-111">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="2ac8f-112">È possibile definire un simbolo ma non è possibile assegnare a questo un valore.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="2ac8f-113">La direttiva `#define` deve essere inserita in un file prima di usare istruzioni che non siano anche direttive del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="2ac8f-114">Un simbolo può anche essere definito tramite l'opzione del compilatore [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2ac8f-114">You can also define a symbol with the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="2ac8f-115">Per rimuovere la definizione di un simbolo, è possibile usare [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="2ac8f-115">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="2ac8f-116">Un simbolo definito tramite `-define` o `#define` non provoca conflitti con una variabile avente lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="2ac8f-117">Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="2ac8f-118">L'ambito di un simbolo creato tramite `#define` è il file in cui il simbolo è stato definito.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="2ac8f-119">Come illustrato nell'esempio seguente, è necessario inserire direttive `#define` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="2ac8f-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="2ac8f-120">Per un esempio su come annullare la definizione di un simbolo, vedere [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="2ac8f-120">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac8f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ac8f-121">See Also</span></span>  
 [<span data-ttu-id="2ac8f-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2ac8f-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2ac8f-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2ac8f-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2ac8f-124">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="2ac8f-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="2ac8f-125">const</span><span class="sxs-lookup"><span data-stu-id="2ac8f-125">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="2ac8f-126">Procedura: Compilare in modo condizionale con traccia e debug</span><span class="sxs-lookup"><span data-stu-id="2ac8f-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)  
 [<span data-ttu-id="2ac8f-127">#undef</span><span class="sxs-lookup"><span data-stu-id="2ac8f-127">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
 [<span data-ttu-id="2ac8f-128">#if</span><span class="sxs-lookup"><span data-stu-id="2ac8f-128">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
