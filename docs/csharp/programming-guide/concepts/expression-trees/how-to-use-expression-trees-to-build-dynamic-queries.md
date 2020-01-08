---
title: Come usare gli alberi delle espressioni per la compilazione diC#query dinamiche ()
ms.date: 07/20/2015
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 6114ec13dd43a7df146b87dda00fba06d6eb870c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635899"
---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-c"></a><span data-ttu-id="d58f2-102">Come usare gli alberi delle espressioni per la compilazione diC#query dinamiche ()</span><span class="sxs-lookup"><span data-stu-id="d58f2-102">How to use expression trees to build dynamic queries (C#)</span></span>
<span data-ttu-id="d58f2-103">In LINQ gli alberi delle espressioni vengono usati per rappresentare query strutturate destinate alle origini dati che implementano <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="d58f2-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="d58f2-104">Il provider LINQ, ad esempio, implementa l'interfaccia <xref:System.Linq.IQueryable%601> per l'esecuzione di query su archivi dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="d58f2-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="d58f2-105">Il compilatore C# compila le query destinate a tali origini dati nel codice di un albero delle espressioni in runtime.</span><span class="sxs-lookup"><span data-stu-id="d58f2-105">The C# compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="d58f2-106">Il provider di query può quindi percorrere la struttura dei dati dell'albero delle espressioni e convertirla in un linguaggio di query adatto all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d58f2-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="d58f2-107">Gli alberi delle espressioni vengono usati in LINQ anche per rappresentare espressioni lambda assegnate a variabili di tipo <xref:System.Linq.Expressions.Expression%601>.</span><span class="sxs-lookup"><span data-stu-id="d58f2-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="d58f2-108">Questo argomento descrive come usare gli alberi delle espressioni per creare query LINQ dinamiche.</span><span class="sxs-lookup"><span data-stu-id="d58f2-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="d58f2-109">Le query dinamiche sono utili quando le specifiche di una query non sono note in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d58f2-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="d58f2-110">Supponiamo ad esempio che un'applicazione offra un'interfaccia utente che consente all'utente finale di specificare uno o più predicati per filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="d58f2-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="d58f2-111">Per usare LINQ per l'esecuzione di query e creare query LINQ in runtime, un'applicazione di questo tipo deve usare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="d58f2-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d58f2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d58f2-112">Example</span></span>  
 <span data-ttu-id="d58f2-113">Nell'esempio seguente viene illustrato come usare alberi delle espressioni per costruire una query su un'origine dati `IQueryable` e quindi eseguirla.</span><span class="sxs-lookup"><span data-stu-id="d58f2-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="d58f2-114">Il codice compila un albero delle espressioni per rappresentare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="d58f2-114">The code builds an expression tree to represent the following query:</span></span>  
  
 ```csharp
 companies.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))
          .OrderBy(company => company)
 ```
  
 <span data-ttu-id="d58f2-115">I metodi factory nello spazio dei nomi <xref:System.Linq.Expressions> vengono usati per creare alberi delle espressioni che rappresentano le espressioni che costituiscono la query complessiva.</span><span class="sxs-lookup"><span data-stu-id="d58f2-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="d58f2-116">Le espressioni che rappresentano le chiamate ai metodi degli operatori query standard fanno riferimento alle implementazioni <xref:System.Linq.Queryable> di questi metodi.</span><span class="sxs-lookup"><span data-stu-id="d58f2-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="d58f2-117">L'albero delle espressioni finale viene passato all'implementazione <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> del provider dell'origine dati `IQueryable` per creare una query eseguibile di tipo `IQueryable`.</span><span class="sxs-lookup"><span data-stu-id="d58f2-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="d58f2-118">I risultati si ottengono enumerando tale variabile di query.</span><span class="sxs-lookup"><span data-stu-id="d58f2-118">The results are obtained by enumerating that query variable.</span></span>  
  
```csharp  
// Add a using directive for System.Linq.Expressions.  
  
string[] companies = { "Consolidated Messenger", "Alpine Ski House", "Southridge Video", "City Power & Light",  
                   "Coho Winery", "Wide World Importers", "Graphic Design Institute", "Adventure Works",  
                   "Humongous Insurance", "Woodgrove Bank", "Margie's Travel", "Northwind Traders",  
                   "Blue Yonder Airlines", "Trey Research", "The Phone Company",  
                   "Wingtip Toys", "Lucerne Publishing", "Fourth Coffee" };  
  
// The IQueryable data to query.  
IQueryable<String> queryableData = companies.AsQueryable<string>();  
  
// Compose the expression tree that represents the parameter to the predicate.  
ParameterExpression pe = Expression.Parameter(typeof(string), "company");  
  
// ***** Where(company => (company.ToLower() == "coho winery" || company.Length > 16)) *****  
// Create an expression tree that represents the expression 'company.ToLower() == "coho winery"'.  
Expression left = Expression.Call(pe, typeof(string).GetMethod("ToLower", System.Type.EmptyTypes));  
Expression right = Expression.Constant("coho winery");  
Expression e1 = Expression.Equal(left, right);  
  
// Create an expression tree that represents the expression 'company.Length > 16'.  
left = Expression.Property(pe, typeof(string).GetProperty("Length"));  
right = Expression.Constant(16, typeof(int));  
Expression e2 = Expression.GreaterThan(left, right);  
  
// Combine the expression trees to create an expression tree that represents the  
// expression '(company.ToLower() == "coho winery" || company.Length > 16)'.  
Expression predicateBody = Expression.OrElse(e1, e2);  
  
// Create an expression tree that represents the expression  
// 'queryableData.Where(company => (company.ToLower() == "coho winery" || company.Length > 16))'  
MethodCallExpression whereCallExpression = Expression.Call(  
    typeof(Queryable),  
    "Where",  
    new Type[] { queryableData.ElementType },  
    queryableData.Expression,  
    Expression.Lambda<Func<string, bool>>(predicateBody, new ParameterExpression[] { pe }));  
// ***** End Where *****  
  
// ***** OrderBy(company => company) *****  
// Create an expression tree that represents the expression  
// 'whereCallExpression.OrderBy(company => company)'  
MethodCallExpression orderByCallExpression = Expression.Call(  
    typeof(Queryable),  
    "OrderBy",  
    new Type[] { queryableData.ElementType, queryableData.ElementType },  
    whereCallExpression,  
    Expression.Lambda<Func<string, string>>(pe, new ParameterExpression[] { pe }));  
// ***** End OrderBy *****  
  
// Create an executable query from the expression tree.  
IQueryable<string> results = queryableData.Provider.CreateQuery<string>(orderByCallExpression);  
  
// Enumerate the results.  
foreach (string company in results)  
    Console.WriteLine(company);  
  
/*  This code produces the following output:  
  
    Blue Yonder Airlines  
    City Power & Light  
    Coho Winery  
    Consolidated Messenger  
    Graphic Design Institute  
    Humongous Insurance  
    Lucerne Publishing  
    Northwind Traders  
    The Phone Company  
    Wide World Importers  
*/  
```  
  
 <span data-ttu-id="d58f2-119">Questo codice usa un numero fisso di espressioni nel predicato passato al metodo `Queryable.Where`.</span><span class="sxs-lookup"><span data-stu-id="d58f2-119">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="d58f2-120">È tuttavia possibile scrivere un'applicazione che combini un numero variabile di espressioni di predicato a seconda dall'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d58f2-120">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="d58f2-121">È anche possibile variare gli operatori query standard chiamati nella query in base all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d58f2-121">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d58f2-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d58f2-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="d58f2-123">Includere lo spazio dei nomi System.Linq.Expressions.</span><span class="sxs-lookup"><span data-stu-id="d58f2-123">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58f2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58f2-124">See also</span></span>

- [<span data-ttu-id="d58f2-125">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="d58f2-125">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="d58f2-126">Come eseguire gli alberi delle espressioniC#()</span><span class="sxs-lookup"><span data-stu-id="d58f2-126">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="d58f2-127">Specificare dinamicamente i filtri dei predicati in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d58f2-127">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
