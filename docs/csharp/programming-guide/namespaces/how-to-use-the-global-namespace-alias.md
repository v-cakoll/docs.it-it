---
title: "Procedura: Usare l'alias dello spazio dei nomi globale - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796285"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="a8b7c-102">Procedura: Usare l'alias dello spazio dei nomi globale (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a8b7c-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="a8b7c-103">La possibilità di accedere a un membro nello [spazio dei nomi globale](../../../csharp/language-reference/keywords/namespace.md) è utile quando il membro può essere nascosto da un'altra entità con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="a8b7c-104">Nel codice seguente, ad esempio, `Console` si risolve in `TestApp.Console` invece che nel tipo `Console` nello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="a8b7c-105">L'uso di `System.Console` causa comunque un errore perché lo spazio dei nomi `System` è nascosto dalla classe `TestApp.System`:</span><span class="sxs-lookup"><span data-stu-id="a8b7c-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="a8b7c-106">È tuttavia possibile evitare questo errore usando `global::System.Console`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a8b7c-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="a8b7c-107">Se l'identificatore di sinistra è `global`, la ricerca dell'identificatore di destra ha inizio dallo spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="a8b7c-108">La seguente dichiarazione fa ad esempio riferimento a `TestApp` come membro dello spazio globale.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="a8b7c-109">Non è ovviamente consigliabile creare spazi dei nomi personali denominati `System` ed è improbabile trovare codice che include uno spazio dei nomi con tale nome.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="a8b7c-110">Nei progetti di grandi dimensioni è tuttavia molto probabile che si verifichi in qualche modo la duplicazione degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="a8b7c-111">In queste situazioni è possibile usare il qualificatore dello spazio dei nomi globale per specificare lo spazio dei nomi radice.</span><span class="sxs-lookup"><span data-stu-id="a8b7c-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b7c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8b7c-112">See also</span></span>

- [<span data-ttu-id="a8b7c-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a8b7c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a8b7c-114">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="a8b7c-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="a8b7c-115">:: (operatore)</span><span class="sxs-lookup"><span data-stu-id="a8b7c-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="a8b7c-116">extern</span><span class="sxs-lookup"><span data-stu-id="a8b7c-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
