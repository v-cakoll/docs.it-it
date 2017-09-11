---
title: 'Procedura: utilizzare strutture ad albero dell&quot;espressione per creare query dinamiche (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="16718-102">Procedura: utilizzare strutture ad albero dell'espressione per creare query dinamiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16718-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>
<span data-ttu-id="16718-103">In LINQ, gli alberi delle espressioni vengono utilizzate per rappresentare le query strutturate destinate alle origini dei dati che implementano <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="16718-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="16718-104">Ad esempio, implementa il provider LINQ di <xref:System.Linq.IQueryable%601>interfaccia per l'esecuzione di query su archivi dati relazionali.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="16718-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="16718-105">Il compilatore Visual Basic vengono compilate in query destinate a tali origini dati nel codice che compila un albero delle espressioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="16718-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="16718-106">Il provider di query può quindi attraversare la struttura di dati ad albero di espressione e convertirla in un linguaggio di query appropriato per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="16718-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="16718-107">Gli alberi delle espressioni vengono utilizzate anche in LINQ per rappresentare le espressioni lambda che vengono assegnate a variabili di tipo <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601></span><span class="sxs-lookup"><span data-stu-id="16718-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="16718-108">In questo argomento viene descritto come utilizzare gli alberi delle espressioni per creare query dinamiche di LINQ.</span><span class="sxs-lookup"><span data-stu-id="16718-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="16718-109">Query dinamiche sono utili quando le specifiche di una query non sono noti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="16718-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="16718-110">Ad esempio, un'applicazione può fornire un'interfaccia utente che consente all'utente finale specificare uno o più predicati per filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="16718-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="16718-111">Per utilizzare LINQ per eseguire la query, questo tipo di applicazione deve utilizzare strutture ad albero dell'espressione per creare la query LINQ in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="16718-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16718-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="16718-112">Example</span></span>  
 <span data-ttu-id="16718-113">Nell'esempio seguente viene illustrato come utilizzare gli alberi delle espressioni per costruire una query su un `IQueryable` origine dati e quindi eseguirla.</span><span class="sxs-lookup"><span data-stu-id="16718-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="16718-114">Il codice verrà compilato un albero delle espressioni per rappresentare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="16718-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 <span data-ttu-id="16718-115">I metodi factory il <xref:System.Linq.Expressions>dello spazio dei nomi vengono utilizzati per creare alberi delle espressioni che rappresentano le espressioni che costituiscono la query.</xref:System.Linq.Expressions></span><span class="sxs-lookup"><span data-stu-id="16718-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="16718-116">Le espressioni che rappresentano le chiamate ai metodi degli operatori di query standard si intende il <xref:System.Linq.Queryable>implementazioni di questi metodi.</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="16718-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="16718-117">L'albero delle espressioni finale viene passato per il <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>implementazione del provider del `IQueryable` origine dati per creare una query eseguibile di tipo `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29></span><span class="sxs-lookup"><span data-stu-id="16718-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="16718-118">I risultati vengono ottenuti enumerando quella variabile di query.</span><span class="sxs-lookup"><span data-stu-id="16718-118">The results are obtained by enumerating that query variable.</span></span>  
  
<span data-ttu-id="16718-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="16718-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="16718-120">Questo codice utilizza un numero fisso di espressioni nel predicato che viene passato per il `Queryable.Where` metodo.</span><span class="sxs-lookup"><span data-stu-id="16718-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="16718-121">Tuttavia, è possibile scrivere un'applicazione che combina un numero variabile di espressioni del predicato che dipende da input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="16718-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="16718-122">È anche possibile modificare gli operatori query standard che vengono chiamati nella query, in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="16718-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16718-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="16718-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="16718-124">Creare un nuovo **applicazione Console** progetto.</span><span class="sxs-lookup"><span data-stu-id="16718-124">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="16718-125">Se non è già presente, aggiungere un riferimento a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="16718-125">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="16718-126">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="16718-126">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="16718-127">Copiare il codice dell'esempio e incollarlo il `Main` `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="16718-127">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16718-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16718-128">See Also</span></span>  
 <span data-ttu-id="16718-129">[Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="16718-129">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="16718-130"> [Procedura: eseguire alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="16718-130"> [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
