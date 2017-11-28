---
title: Eseguire join raggruppati
description: Come eseguire join raggruppati.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 5e26473e19a5b6107d7aceea5e9829b48aa522b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="perform-grouped-joins"></a><span data-ttu-id="3eee5-104">Eseguire join raggruppati</span><span class="sxs-lookup"><span data-stu-id="3eee5-104">Perform grouped joins</span></span>

<span data-ttu-id="3eee5-105">Il join di gruppo è utile per produrre strutture di dati gerarchiche.</span><span class="sxs-lookup"><span data-stu-id="3eee5-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="3eee5-106">Abbina ogni elemento della prima raccolta con un set di elementi correlati della seconda raccolta.</span><span class="sxs-lookup"><span data-stu-id="3eee5-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="3eee5-107">Ad esempio, una classe o una tabella di database relazionale denominata `Student` potrebbe contenere due campi: `Id` e `Name`.</span><span class="sxs-lookup"><span data-stu-id="3eee5-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="3eee5-108">Un'altra classe o tabella di database relazionale denominata `Course` potrebbe contenere due campi: `StudentId` e `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="3eee5-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="3eee5-109">Un join di gruppo di queste due origini dati, basato sulla corrispondenza di `Student.Id` e `Course.StudentId` raggrupperebbe ogni `Student` con una raccolta di oggetti `Course` (che può essere vuota).</span><span class="sxs-lookup"><span data-stu-id="3eee5-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eee5-110">Ogni elemento della prima raccolta viene visualizzato nel set di risultati di un join di gruppo indipendentemente dal fatto che gli elementi correlati vengano trovati nella seconda raccolta.</span><span class="sxs-lookup"><span data-stu-id="3eee5-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="3eee5-111">Nel caso in cui non venga trovato alcun elemento correlato, la sequenza di elementi correlati per l'elemento è vuota.</span><span class="sxs-lookup"><span data-stu-id="3eee5-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="3eee5-112">Il selettore del risultato ha pertanto accesso a ogni elemento della prima raccolta.</span><span class="sxs-lookup"><span data-stu-id="3eee5-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="3eee5-113">È diverso dal selettore del risultato in un join non di gruppo, che non può accedere a elementi della prima raccolta che non hanno corrispondenza nella seconda raccolta.</span><span class="sxs-lookup"><span data-stu-id="3eee5-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="3eee5-114">Il primo esempio in questo argomento illustra come eseguire un join di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3eee5-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="3eee5-115">Il secondo esempio descrive come usare un join di gruppo per creare elementi XML.</span><span class="sxs-lookup"><span data-stu-id="3eee5-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eee5-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3eee5-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="3eee5-117">Esempio di join di gruppo</span><span class="sxs-lookup"><span data-stu-id="3eee5-117">Group join example</span></span>  
 <span data-ttu-id="3eee5-118">L'esempio seguente esegue un join di gruppo di oggetti di tipo `Person` e `Pet` basato su `Person` corrispondente alla proprietà `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="3eee5-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="3eee5-119">Diversamente da un join non di gruppo che produrrebbe una coppia di elementi per ogni corrispondenza, il join di gruppo produce un solo oggetto risultante per ogni elemento della prima raccolta, che in questo esempio è un oggetto `Person`.</span><span class="sxs-lookup"><span data-stu-id="3eee5-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="3eee5-120">Gli elementi corrispondenti della seconda raccolta, che in questo esempio sono oggetti `Pet` vengono raggruppati in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3eee5-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="3eee5-121">La funzione del selettore del risultato crea infine un tipo anonimo per ogni corrispondenza costituita da `Person.FirstName` e una raccolta di oggetti `Pet`.</span><span class="sxs-lookup"><span data-stu-id="3eee5-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3eee5-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="3eee5-122">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="3eee5-123">Esempio di join di gruppo per la creazione di XML</span><span class="sxs-lookup"><span data-stu-id="3eee5-123">Group join to create XML example</span></span>  
 <span data-ttu-id="3eee5-124">I join di gruppo sono ideali per la creazione di XML tramite LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="3eee5-124">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="3eee5-125">L'esempio seguente è simile a quello precedente tranne per il fatto che, invece di creare tipi anonimi, la funzione del selettore del risultato crea elementi XML che rappresentano gli oggetti uniti in join.</span><span class="sxs-lookup"><span data-stu-id="3eee5-125">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="3eee5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eee5-126">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="3eee5-127">Eseguire inner join</span><span class="sxs-lookup"><span data-stu-id="3eee5-127">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="3eee5-128">Eseguire left outer join</span><span class="sxs-lookup"><span data-stu-id="3eee5-128">Perform left outer joins</span></span>](perform-left-outer-joins.md)  
 [<span data-ttu-id="3eee5-129">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="3eee5-129">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
