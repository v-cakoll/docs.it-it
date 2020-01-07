---
title: "Procedura: utilizzare strutture ad albero dell'espressione per la compilazione di query dinamiche"
ms.date: 07/20/2015
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: 616aa3eba1e07a92983bb5d2048a9dbae936e77c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346059"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="cfa76-102">Procedura: usare alberi delle espressioni per la compilazione di query dinamiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfa76-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>

<span data-ttu-id="cfa76-103">In LINQ gli alberi delle espressioni vengono usati per rappresentare query strutturate destinate alle origini dati che implementano <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="cfa76-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="cfa76-104">Il provider LINQ, ad esempio, implementa l'interfaccia <xref:System.Linq.IQueryable%601> per l'esecuzione di query su archivi dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="cfa76-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="cfa76-105">Il compilatore Visual Basic Compila query destinate a tali origini dati in codice che compila un albero delle espressioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cfa76-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="cfa76-106">Il provider di query può quindi percorrere la struttura dei dati dell'albero delle espressioni e convertirla in un linguaggio di query adatto all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cfa76-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>

<span data-ttu-id="cfa76-107">Gli alberi delle espressioni vengono usati in LINQ anche per rappresentare espressioni lambda assegnate a variabili di tipo <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="cfa76-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>

<span data-ttu-id="cfa76-108">Questo argomento descrive come usare gli alberi delle espressioni per creare query LINQ dinamiche.</span><span class="sxs-lookup"><span data-stu-id="cfa76-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="cfa76-109">Le query dinamiche sono utili quando le specifiche di una query non sono note in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cfa76-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="cfa76-110">Supponiamo ad esempio che un'applicazione offra un'interfaccia utente che consente all'utente finale di specificare uno o più predicati per filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="cfa76-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="cfa76-111">Per usare LINQ per l'esecuzione di query e creare query LINQ in runtime, un'applicazione di questo tipo deve usare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="cfa76-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>

## <a name="example"></a><span data-ttu-id="cfa76-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfa76-112">Example</span></span>

<span data-ttu-id="cfa76-113">Nell'esempio seguente viene illustrato come usare alberi delle espressioni per costruire una query su un'origine dati `IQueryable` e quindi eseguirla.</span><span class="sxs-lookup"><span data-stu-id="cfa76-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="cfa76-114">Il codice compila un albero delle espressioni per rappresentare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="cfa76-114">The code builds an expression tree to represent the following query:</span></span>

`companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`

<span data-ttu-id="cfa76-115">I metodi factory nello spazio dei nomi <xref:System.Linq.Expressions> vengono usati per creare alberi delle espressioni che rappresentano le espressioni che costituiscono la query complessiva.</span><span class="sxs-lookup"><span data-stu-id="cfa76-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="cfa76-116">Le espressioni che rappresentano le chiamate ai metodi degli operatori query standard fanno riferimento alle implementazioni <xref:System.Linq.Queryable> di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="cfa76-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="cfa76-117">L'albero delle espressioni finale viene passato all'implementazione <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del provider dell'origine dati `IQueryable` per creare una query eseguibile di tipo `IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="cfa76-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="cfa76-118">I risultati si ottengono enumerando tale variabile di query.</span><span class="sxs-lookup"><span data-stu-id="cfa76-118">The results are obtained by enumerating that query variable.</span></span>

```vb
' Add an Imports statement for System.Linq.Expressions.

Dim companies =
    {"Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",
     "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",
     "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",
     "Blue Yonder Airlines", "Trey Research", "The Phone Company",
     "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee"}

' The IQueryable data to query.
Dim queryableData As IQueryable(Of String) = companies.AsQueryable()

' Compose the expression tree that represents the parameter to the predicate.
Dim pe As ParameterExpression = Expression.Parameter(GetType(String), "company")

' ***** Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16) *****
' Create an expression tree that represents the expression: company.ToLower() = "coho winery".
Dim left As Expression = Expression.Call(pe, GetType(String).GetMethod("ToLower", System.Type.EmptyTypes))
Dim right As Expression = Expression.Constant("coho winery")
Dim e1 As Expression = Expression.Equal(left, right)

' Create an expression tree that represents the expression: company.Length > 16.
left = Expression.Property(pe, GetType(String).GetProperty("Length"))
right = Expression.Constant(16, GetType(Integer))
Dim e2 As Expression = Expression.GreaterThan(left, right)

' Combine the expressions to create an expression tree that represents the
' expression: company.ToLower() = "coho winery" OrElse company.Length > 16).
Dim predicateBody As Expression = Expression.OrElse(e1, e2)

' Create an expression tree that represents the expression:
' queryableData.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16)
Dim whereCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "Where",
        New Type() {queryableData.ElementType},
        queryableData.Expression,
        Expression.Lambda(Of Func(Of String, Boolean))(predicateBody, New ParameterExpression() {pe}))
' ***** End Where *****

' ***** OrderBy(Function(company) company) *****
' Create an expression tree that represents the expression:
' whereCallExpression.OrderBy(Function(company) company)
Dim orderByCallExpression As MethodCallExpression = Expression.Call(
        GetType(Queryable),
        "OrderBy",
        New Type() {queryableData.ElementType, queryableData.ElementType},
        whereCallExpression,
        Expression.Lambda(Of Func(Of String, String))(pe, New ParameterExpression() {pe}))
' ***** End OrderBy *****

' Create an executable query from the expression tree.
Dim results As IQueryable(Of String) = queryableData.Provider.CreateQuery(Of String)(orderByCallExpression)

' Enumerate the results.
For Each company As String In results
    Console.WriteLine(company)
Next

' This code produces the following output:
'
' Blue Yonder Airlines
' City Power & Light
' Coho Winery
' Consolidated Messenger
' Graphic Design Institute
' Humongous Insurance
' Lucerne Publishing
' Northwind Traders
' The Phone Company
' Wide World Importers
```

<span data-ttu-id="cfa76-119">Questo codice usa un numero fisso di espressioni nel predicato passato al metodo `Queryable.Where`.</span><span class="sxs-lookup"><span data-stu-id="cfa76-119">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="cfa76-120">È tuttavia possibile scrivere un'applicazione che combini un numero variabile di espressioni di predicato a seconda dall'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cfa76-120">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="cfa76-121">È anche possibile variare gli operatori query standard chiamati nella query in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cfa76-121">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="cfa76-122">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="cfa76-122">Compile the code</span></span>

- <span data-ttu-id="cfa76-123">Creare un nuovo progetto **applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="cfa76-123">Create a new **Console Application** project.</span></span>

- <span data-ttu-id="cfa76-124">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="cfa76-124">Include the System.Linq.Expressions namespace.</span></span>

- <span data-ttu-id="cfa76-125">Copiare il codice dall'esempio e incollarlo nella procedura `Main` `Sub`.</span><span class="sxs-lookup"><span data-stu-id="cfa76-125">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfa76-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfa76-126">See also</span></span>

- [<span data-ttu-id="cfa76-127">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfa76-127">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="cfa76-128">Procedura: eseguire alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfa76-128">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
