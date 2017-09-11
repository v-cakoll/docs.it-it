---
title: namespace (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
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
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="260b2-102">namespace (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="260b2-102">namespace (C# Reference)</span></span>
<span data-ttu-id="260b2-103">La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="260b2-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="260b2-104">È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="260b2-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="260b2-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="260b2-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="260b2-106">Note</span><span class="sxs-lookup"><span data-stu-id="260b2-106">Remarks</span></span>  
 <span data-ttu-id="260b2-107">All'interno di uno spazio dei nomi, è possibile dichiarare uno o più dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="260b2-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="260b2-108">un altro spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="260b2-108">another namespace</span></span>  
  
-   [<span data-ttu-id="260b2-109">class</span><span class="sxs-lookup"><span data-stu-id="260b2-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="260b2-110">interface</span><span class="sxs-lookup"><span data-stu-id="260b2-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="260b2-111">struct</span><span class="sxs-lookup"><span data-stu-id="260b2-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="260b2-112">enum</span><span class="sxs-lookup"><span data-stu-id="260b2-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="260b2-113">delegate</span><span class="sxs-lookup"><span data-stu-id="260b2-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="260b2-114">Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="260b2-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="260b2-115">Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file.</span><span class="sxs-lookup"><span data-stu-id="260b2-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="260b2-116">Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="260b2-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="260b2-117">Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile.</span><span class="sxs-lookup"><span data-stu-id="260b2-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="260b2-118">Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="260b2-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="260b2-119">È possibile definire uno spazio dei nomi in una o più dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="260b2-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="260b2-120">L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="260b2-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="260b2-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="260b2-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="260b2-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="260b2-122">Example</span></span>  
 <span data-ttu-id="260b2-123">L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="260b2-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="260b2-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="260b2-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="260b2-125">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="260b2-125">For More Information</span></span>  
 <span data-ttu-id="260b2-126">Per altre informazioni sull'uso degli spazi dei nomi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="260b2-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="260b2-127">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="260b2-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="260b2-128">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="260b2-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="260b2-129">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="260b2-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="260b2-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="260b2-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="260b2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="260b2-131">See Also</span></span>  
 <span data-ttu-id="260b2-132">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="260b2-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="260b2-133">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="260b2-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="260b2-134">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="260b2-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="260b2-135">[Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="260b2-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="260b2-136">using</span><span class="sxs-lookup"><span data-stu-id="260b2-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

