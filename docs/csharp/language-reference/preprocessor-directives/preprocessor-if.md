---
title: '#<a name="if-c-reference"></a>if (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a><span data-ttu-id="3a0ce-102">#if (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3a0ce-102">#if (C# Reference)</span></span>
<span data-ttu-id="3a0ce-103">Quando il compilatore C# trova una direttiva `#if` seguita da una direttiva [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), compila il codice tra tali direttive solo se il simbolo specificato è definito.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="3a0ce-104">A differenza di C e C++, non è possibile assegnare un valore numerico a un simbolo. L'istruzione #if in C# è booleana e consente di verificare solo se il simbolo è stato o meno definito.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="3a0ce-105">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="3a0ce-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="3a0ce-106">È possibile usare gli operatori [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (uguaglianza), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (disuguaglianza) solo per verificare se una condizione è [true](../../../csharp/language-reference/keywords/true.md) o [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="3a0ce-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="3a0ce-107">True significa che il simbolo è definito.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-107">True means the symbol is defined.</span></span> <span data-ttu-id="3a0ce-108">L'istruzione `#if DEBUG` ha lo stesso significato di `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="3a0ce-109">È possibile usare gli operatori [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or) e [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="3a0ce-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="3a0ce-110">(not) per stabilire se sono stati definiti più simboli.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="3a0ce-111">È anche possibile raggruppare simboli e operatori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a0ce-112">Note</span><span class="sxs-lookup"><span data-stu-id="3a0ce-112">Remarks</span></span>  
 <span data-ttu-id="3a0ce-113">`#if`, nsieme alle direttive [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) e [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), consente di includere o escludere il codice in base all'esistenza di uno o più simboli.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="3a0ce-114">Questo può essere utile quando si compila il codice per una build di debug o per una configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="3a0ce-115">Una direttiva condizionale che inizia con `#if` deve terminare in modo esplicito con una direttiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="3a0ce-116">`#define` consente di definire un simbolo. In questo modo, usando il simbolo come espressione passata alla direttiva `#if`, l'espressione restituirà `true`.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="3a0ce-117">Un simbolo può anche essere definito tramite l'opzione del compilatore [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3a0ce-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="3a0ce-118">Per rimuovere la definizione di un simbolo, è possibile usare [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="3a0ce-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="3a0ce-119">Un simbolo definito tramite `/define` o `#define` non provoca conflitti con una variabile avente lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="3a0ce-120">Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="3a0ce-121">L'ambito di un simbolo creato con `#define` è il file in cui è stato definito.</span><span class="sxs-lookup"><span data-stu-id="3a0ce-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a0ce-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a0ce-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="3a0ce-123">**Sono stati definiti DEBUG e MYTEST**</span><span class="sxs-lookup"><span data-stu-id="3a0ce-123">**DEBUG and MYTEST are defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="3a0ce-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a0ce-124">See Also</span></span>  
 [<span data-ttu-id="3a0ce-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3a0ce-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3a0ce-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a0ce-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3a0ce-127">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="3a0ce-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
