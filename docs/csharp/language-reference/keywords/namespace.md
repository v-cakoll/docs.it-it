---
title: namespace (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 343cce85dd235532fbe3fc90af0a785f48518db7
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245615"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="81b25-102">namespace (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="81b25-102">namespace (C# Reference)</span></span>
<span data-ttu-id="81b25-103">La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="81b25-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="81b25-104">È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="81b25-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="81b25-105">Note</span><span class="sxs-lookup"><span data-stu-id="81b25-105">Remarks</span></span>  
 <span data-ttu-id="81b25-106">All'interno di uno spazio dei nomi, è possibile dichiarare uno o più dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="81b25-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="81b25-107">un altro spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="81b25-107">another namespace</span></span>  
  
-   [<span data-ttu-id="81b25-108">class</span><span class="sxs-lookup"><span data-stu-id="81b25-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="81b25-109">interface</span><span class="sxs-lookup"><span data-stu-id="81b25-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="81b25-110">struct</span><span class="sxs-lookup"><span data-stu-id="81b25-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="81b25-111">enum</span><span class="sxs-lookup"><span data-stu-id="81b25-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="81b25-112">delegate</span><span class="sxs-lookup"><span data-stu-id="81b25-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="81b25-113">Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="81b25-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="81b25-114">Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file.</span><span class="sxs-lookup"><span data-stu-id="81b25-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="81b25-115">Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="81b25-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="81b25-116">Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile.</span><span class="sxs-lookup"><span data-stu-id="81b25-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="81b25-117">Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="81b25-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="81b25-118">È possibile definire uno spazio dei nomi in una o più dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="81b25-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="81b25-119">L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="81b25-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="81b25-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="81b25-120">Example</span></span>  
 <span data-ttu-id="81b25-121">L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="81b25-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="81b25-122">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="81b25-122">For More Information</span></span>  
 <span data-ttu-id="81b25-123">Per altre informazioni sull'uso degli spazi dei nomi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="81b25-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="81b25-124">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="81b25-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="81b25-125">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="81b25-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="81b25-126">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="81b25-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="81b25-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="81b25-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="81b25-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b25-128">See Also</span></span>  
 [<span data-ttu-id="81b25-129">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="81b25-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="81b25-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="81b25-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="81b25-131">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="81b25-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="81b25-132">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="81b25-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="81b25-133">using</span><span class="sxs-lookup"><span data-stu-id="81b25-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
