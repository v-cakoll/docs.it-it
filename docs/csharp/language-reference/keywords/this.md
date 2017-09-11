---
title: this (Riferimenti per C#)
description: Parola chiave this (Riferimenti per C#)
keywords: this (C#), parola chiave this (C#), parola chiave this (Riferimenti per C#), parola chiave this (Riferimenti per il linguaggio C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
ms.openlocfilehash: 1e764bbd85d06a3b1898f6574064b2844f6d6813
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="this-c-reference"></a><span data-ttu-id="41de3-104">this (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="41de3-104">this (C# Reference)</span></span>
<span data-ttu-id="41de3-105">La parola chiave `this` fa riferimento all'istanza corrente della classe e viene anche usata come modificatore del primo parametro di un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="41de3-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41de3-106">Questo articolo illustra l'uso di `this` con istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="41de3-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="41de3-107">Per altre informazioni sull'uso nei metodi di estensione, vedere [Metodi di estensione](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="41de3-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="41de3-108">Di seguito sono riportati gli usi comuni di `this`:</span><span class="sxs-lookup"><span data-stu-id="41de3-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="41de3-109">Per qualificare i membri nascosti da nomi simili, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41de3-109">To qualify members hidden by similar names, for example:</span></span>  
  
 <span data-ttu-id="41de3-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41de3-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span></span>  
  
-   <span data-ttu-id="41de3-111">Per passare un oggetto come parametro ad altri metodi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41de3-111">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="41de3-112">Per dichiarare gli indicizzatori, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="41de3-112">To declare indexers, for example:</span></span>  
  
 <span data-ttu-id="41de3-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="41de3-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span></span>  
  
 <span data-ttu-id="41de3-114">Le funzioni del membro statico, perché esistono a livello di classe e non come parte di un oggetto, non dispongono di un puntatore `this`.</span><span class="sxs-lookup"><span data-stu-id="41de3-114">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="41de3-115">È un errore fare riferimento a `this` in un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="41de3-115">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41de3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="41de3-116">Example</span></span>  
 <span data-ttu-id="41de3-117">In questo esempio, `this` viene usato per qualificare i membri della classe `Employee`, `name` e `alias`, che sono nascosti da nomi simili.</span><span class="sxs-lookup"><span data-stu-id="41de3-117">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="41de3-118">Viene anche usato per passare un oggetto al metodo `CalcTax`, che appartiene a un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="41de3-118">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 <span data-ttu-id="41de3-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="41de3-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="41de3-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="41de3-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41de3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41de3-121">See Also</span></span>  
 <span data-ttu-id="41de3-122">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="41de3-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="41de3-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="41de3-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="41de3-124">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="41de3-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="41de3-125">[base](../../../csharp/language-reference/keywords/base.md) </span><span class="sxs-lookup"><span data-stu-id="41de3-125">[base](../../../csharp/language-reference/keywords/base.md) </span></span>  
 [<span data-ttu-id="41de3-126">Metodi</span><span class="sxs-lookup"><span data-stu-id="41de3-126">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

