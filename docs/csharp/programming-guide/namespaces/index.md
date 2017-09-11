---
title: Spazi dei nomi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
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
ms.openlocfilehash: a45339a4c3320a92c0339b1cad6345a2555ed920
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="05414-102">Spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="05414-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="05414-103">Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="05414-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="05414-104">Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="05414-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 <span data-ttu-id="05414-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="05414-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="05414-106">`System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="05414-106">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="05414-107">Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="05414-107">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 <span data-ttu-id="05414-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="05414-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span></span>  
  
 <span data-ttu-id="05414-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="05414-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span></span>  
  
 <span data-ttu-id="05414-110">Per altre informazioni, vedere la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="05414-110">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="05414-111">Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="05414-111">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="05414-112">Usare la parola chiave [namespace](../../../csharp/language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="05414-112">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 <span data-ttu-id="05414-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="05414-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span></span>  
  
## <a name="namespaces-overview"></a><span data-ttu-id="05414-114">Panoramica degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="05414-114">Namespaces Overview</span></span>  
 <span data-ttu-id="05414-115">Gli spazi dei nomi hanno le proprietà riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="05414-115">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="05414-116">Consentono di organizzare progetti di codice di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="05414-116">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="05414-117">Vengono delimitati usando l'operatore `.`.</span><span class="sxs-lookup"><span data-stu-id="05414-117">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="05414-118">`using directive` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.</span><span class="sxs-lookup"><span data-stu-id="05414-118">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="05414-119">Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi `System` di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05414-119">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05414-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="05414-120">Related Sections</span></span>  
 <span data-ttu-id="05414-121">Per altre informazioni sugli spazi dei nomi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="05414-121">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="05414-122">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="05414-122">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="05414-123">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="05414-123">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="05414-124">Procedura: Usare lo spazio dei nomi My</span><span class="sxs-lookup"><span data-stu-id="05414-124">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="05414-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="05414-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05414-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05414-126">See Also</span></span>  
 <span data-ttu-id="05414-127">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="05414-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="05414-128">[Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="05414-128">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="05414-129">[Direttiva using](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="05414-129">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="05414-130">[Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="05414-130">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="05414-131">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="05414-131">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)

