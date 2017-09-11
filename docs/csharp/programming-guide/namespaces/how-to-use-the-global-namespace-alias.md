---
title: 'Procedura: utilizzare l''alias dello spazio dei nomi globale (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
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
ms.openlocfilehash: 1252fc107d46b1d3a1cbef0a61708edc57253910
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="a4f49-102">Procedura: utilizzare l'alias dello spazio dei nomi globale (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a4f49-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="a4f49-103">La possibilità di accedere a un membro nello [spazio dei nomi globale](../../../csharp/language-reference/keywords/namespace.md) è utile quando il membro può essere nascosto da un'altra entità con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="a4f49-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="a4f49-104">Nel codice seguente, ad esempio, `Console` si risolve in `TestApp.Console` invece che nel tipo `Console` nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="a4f49-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 <span data-ttu-id="a4f49-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-105">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-106">[!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-107">L'uso di `System.Console` causa comunque un errore perché lo spazio dei nomi `System` è nascosto dalla classe `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="a4f49-107">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 <span data-ttu-id="a4f49-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-108">[!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-109">È tuttavia possibile evitare questo errore usando `global::System.Console`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a4f49-109">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 <span data-ttu-id="a4f49-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-110">[!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-111">Se l'identificatore di sinistra è `global`, la ricerca dell'identificatore di destra ha inizio dallo spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="a4f49-111">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="a4f49-112">La seguente dichiarazione fa ad esempio riferimento a `TestApp` come membro dello spazio globale.</span><span class="sxs-lookup"><span data-stu-id="a4f49-112">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 <span data-ttu-id="a4f49-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-113">[!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-114">Non è ovviamente consigliabile creare spazi dei nomi personali denominati `System` ed è improbabile trovare codice che include uno spazio dei nomi con tale nome.</span><span class="sxs-lookup"><span data-stu-id="a4f49-114">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="a4f49-115">Nei progetti di grandi dimensioni è tuttavia molto probabile che si verifichi in qualche modo la duplicazione degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a4f49-115">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="a4f49-116">In queste situazioni è possibile usare il qualificatore dello spazio dei nomi globale per specificare lo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="a4f49-116">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4f49-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4f49-117">Example</span></span>  
 <span data-ttu-id="a4f49-118">In questo esempio viene usato lo spazio dei nomi `System` per includere la classe `TestClass`. Di conseguenza, è necessario usare `global::System.Console` per fare riferimento alla classe `System.Console`, nascosta dallo spazio dei nomi `System`.</span><span class="sxs-lookup"><span data-stu-id="a4f49-118">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="a4f49-119">Viene inoltre usato l'alias `colAlias` per fare riferimento allo spazio dei nomi `System.Collections`. Di conseguenza, l'istanza di un oggetto <xref:System.Collections.Hashtable?displayProperty=fullName> è stata creata usando questo alias invece dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a4f49-119">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=fullName> was created using this alias instead of the namespace.</span></span>  
  
 <span data-ttu-id="a4f49-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4f49-120">[!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]</span></span>  
  
 <span data-ttu-id="a4f49-121">**A 1**</span><span class="sxs-lookup"><span data-stu-id="a4f49-121">**A 1**</span></span>  
<span data-ttu-id="a4f49-122">**B 2**</span><span class="sxs-lookup"><span data-stu-id="a4f49-122">**B 2**</span></span>  
<span data-ttu-id="a4f49-123">**C 3**</span><span class="sxs-lookup"><span data-stu-id="a4f49-123">**C 3**</span></span>   
## <a name="see-also"></a><span data-ttu-id="a4f49-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4f49-124">See Also</span></span>  
 <span data-ttu-id="a4f49-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4f49-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a4f49-126">[Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4f49-126">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="a4f49-127">[. Operatore](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a4f49-127">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="a4f49-128">[Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="a4f49-128">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="a4f49-129">extern</span><span class="sxs-lookup"><span data-stu-id="a4f49-129">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

