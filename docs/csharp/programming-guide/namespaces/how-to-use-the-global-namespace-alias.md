---
title: "Procedura: Usare l'alias dello spazio dei nomi globale - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: e01f8d5e8868c11a88d99c42fba06d8fefa5dc92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491689"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="74f11-102">Procedura: Usare l'alias dello spazio dei nomi globale (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="74f11-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="74f11-103">La possibilità di accedere a un membro nello [spazio dei nomi globale](../../../csharp/language-reference/keywords/namespace.md) è utile quando il membro può essere nascosto da un'altra entità con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="74f11-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="74f11-104">Nel codice seguente, ad esempio, `Console` si risolve in `TestApp.Console` invece che nel tipo `Console` nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="74f11-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 <span data-ttu-id="74f11-105">L'uso di `System.Console` causa comunque un errore perché lo spazio dei nomi `System` è nascosto dalla classe `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="74f11-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 <span data-ttu-id="74f11-106">È tuttavia possibile evitare questo errore usando `global::System.Console`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="74f11-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 <span data-ttu-id="74f11-107">Se l'identificatore di sinistra è `global`, la ricerca dell'identificatore di destra ha inizio dallo spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="74f11-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="74f11-108">La seguente dichiarazione fa ad esempio riferimento a `TestApp` come membro dello spazio globale.</span><span class="sxs-lookup"><span data-stu-id="74f11-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 <span data-ttu-id="74f11-109">Non è ovviamente consigliabile creare spazi dei nomi personali denominati `System` ed è improbabile trovare codice che include uno spazio dei nomi con tale nome.</span><span class="sxs-lookup"><span data-stu-id="74f11-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="74f11-110">Nei progetti di grandi dimensioni è tuttavia molto probabile che si verifichi in qualche modo la duplicazione degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="74f11-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="74f11-111">In queste situazioni è possibile usare il qualificatore dello spazio dei nomi globale per specificare lo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="74f11-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74f11-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="74f11-112">Example</span></span>  
 <span data-ttu-id="74f11-113">In questo esempio viene usato lo spazio dei nomi `System` per includere la classe `TestClass`. Di conseguenza, è necessario usare `global::System.Console` per fare riferimento alla classe `System.Console`, nascosta dallo spazio dei nomi `System`.</span><span class="sxs-lookup"><span data-stu-id="74f11-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="74f11-114">Viene inoltre usato l'alias `colAlias` per fare riferimento allo spazio dei nomi `System.Collections`. Di conseguenza, l'istanza di un oggetto <xref:System.Collections.Hashtable?displayProperty=nameWithType> è stata creata usando questo alias invece dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="74f11-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
<span data-ttu-id="74f11-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="74f11-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="74f11-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74f11-116">See also</span></span>

- [<span data-ttu-id="74f11-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="74f11-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="74f11-118">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="74f11-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="74f11-119">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="74f11-119">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
- [<span data-ttu-id="74f11-120">:: (operatore)</span><span class="sxs-lookup"><span data-stu-id="74f11-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="74f11-121">extern</span><span class="sxs-lookup"><span data-stu-id="74f11-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
