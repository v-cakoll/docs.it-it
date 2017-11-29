---
title: Spazi dei nomi (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3eb645f5beb61d3cec97a70a54e660c65be52091
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="86c38-102">Spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="86c38-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="86c38-103">Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="86c38-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="86c38-104">Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="86c38-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="86c38-105">`System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="86c38-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="86c38-106">Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86c38-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="86c38-107">Per altre informazioni, vedere la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="86c38-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="86c38-108">Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="86c38-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="86c38-109">Usare la parola chiave [namespace](../../../csharp/language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86c38-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="86c38-110">Panoramica degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="86c38-110">Namespaces Overview</span></span>  
 <span data-ttu-id="86c38-111">Gli spazi dei nomi hanno le proprietà riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="86c38-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="86c38-112">Consentono di organizzare progetti di codice di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="86c38-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="86c38-113">Vengono delimitati usando l'operatore `.`.</span><span class="sxs-lookup"><span data-stu-id="86c38-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="86c38-114">`using directive` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.</span><span class="sxs-lookup"><span data-stu-id="86c38-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="86c38-115">Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi `System` di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86c38-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="86c38-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="86c38-116">Related Sections</span></span>  
 <span data-ttu-id="86c38-117">Per altre informazioni sugli spazi dei nomi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86c38-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="86c38-118">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="86c38-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="86c38-119">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="86c38-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="86c38-120">Procedura: Usare lo spazio dei nomi My</span><span class="sxs-lookup"><span data-stu-id="86c38-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="86c38-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="86c38-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86c38-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86c38-122">See Also</span></span>  
 [<span data-ttu-id="86c38-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="86c38-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="86c38-124">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="86c38-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="86c38-125">Direttiva using</span><span class="sxs-lookup"><span data-stu-id="86c38-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="86c38-126">Operatore ::</span><span class="sxs-lookup"><span data-stu-id="86c38-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="86c38-127">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="86c38-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
