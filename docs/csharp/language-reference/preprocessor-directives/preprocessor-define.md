---
title: '#<a name="define-c-reference"></a>define (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
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
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="6c0f0-102">#define (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6c0f0-102">#define (C# Reference)</span></span>
<span data-ttu-id="6c0f0-103">Si usa `#define` per definire un simbolo.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="6c0f0-104">Quando si usa il simbolo come espressione passata alla direttiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), l'espressione restituisce `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="6c0f0-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="6c0f0-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="6c0f0-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c0f0-106">Note</span><span class="sxs-lookup"><span data-stu-id="6c0f0-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c0f0-107">Non è possibile usare la direttiva `#define` per dichiarare valori costanti come in C e in C++.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="6c0f0-108">Le costanti in C# possono essere definite come membri statici di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="6c0f0-109">Se sono presenti più costanti di questo tipo, per usarle può essere utile creare una classe di costanti separata.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="6c0f0-110">Per specificare le condizioni per la compilazione è possibile usare simboli.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="6c0f0-111">È possibile eseguire il test del simbolo tramite [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="6c0f0-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="6c0f0-112">È anche possibile usare l'attributo `conditional` per eseguire una compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="6c0f0-113">È possibile definire un simbolo ma non è possibile assegnare a questo un valore.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="6c0f0-114">La direttiva `#define` deve essere inserita in un file prima di usare istruzioni che non siano anche direttive del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="6c0f0-115">Un simbolo può anche essere definito tramite l'opzione del compilatore [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6c0f0-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="6c0f0-116">Per rimuovere la definizione di un simbolo, è possibile usare [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="6c0f0-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="6c0f0-117">Un simbolo definito tramite `/define` o `#define` non provoca conflitti con una variabile avente lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="6c0f0-118">Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="6c0f0-119">L'ambito di un simbolo creato tramite `#define` è il file in cui il simbolo è stato definito.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="6c0f0-120">Come illustrato nell'esempio seguente, è necessario inserire direttive `#define` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="6c0f0-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="6c0f0-121">Per un esempio su come annullare la definizione di un simbolo, vedere [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="6c0f0-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0f0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c0f0-122">See Also</span></span>  
 <span data-ttu-id="6c0f0-123">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6c0f0-124">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6c0f0-125">[Direttive per il preprocessore C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="6c0f0-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="6c0f0-127">[Procedura: Compilare in modo condizionale con traccia e debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="6c0f0-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="6c0f0-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="6c0f0-129">#if</span><span class="sxs-lookup"><span data-stu-id="6c0f0-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

