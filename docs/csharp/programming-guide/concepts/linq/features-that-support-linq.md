---
title: Funzionalità di C# che supportano LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 32ba8f5e60b3ed2efd813a8ae32e5f4009eb790d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202412"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="6abc8-102">Funzionalità di C# che supportano LINQ</span><span class="sxs-lookup"><span data-stu-id="6abc8-102">C# Features That Support LINQ</span></span>

<span data-ttu-id="6abc8-103">Nella sezione seguente vengono illustrati i nuovi costrutti di linguaggio introdotti in C# 3.0.</span><span class="sxs-lookup"><span data-stu-id="6abc8-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="6abc8-104">Anche se queste nuove funzionalità sono tutte usate per un grado di query LINQ, non sono limitate a LINQ e possono essere usate in qualsiasi contesto in cui si trovano utili.</span><span class="sxs-lookup"><span data-stu-id="6abc8-104">Although these new features are all used to a degree with LINQ queries, they are not limited to LINQ and can be used in any context where you find them useful.</span></span>

## <a name="query-expressions"></a><span data-ttu-id="6abc8-105">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="6abc8-105">Query Expressions</span></span>

<span data-ttu-id="6abc8-106">Le espressioni di query usano una sintassi dichiarativa simile a SQL o XQuery per eseguire una query sulle raccolte IEnumerable.</span><span class="sxs-lookup"><span data-stu-id="6abc8-106">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="6abc8-107">In fase di compilazione la sintassi di query viene convertita in chiamate al metodo nell'implementazione di un provider LINQ dei metodi di estensione degli operatori di query standard.</span><span class="sxs-lookup"><span data-stu-id="6abc8-107">At compile time query syntax is converted to method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="6abc8-108">Le applicazioni controllano gli operatori di query standard inclusi nell'ambito specificando lo spazio dei nomi adatto con una direttiva `using`.</span><span class="sxs-lookup"><span data-stu-id="6abc8-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="6abc8-109">Nell'espressione di query seguente viene usata una matrice di stringhe, raggruppate in base al primo carattere della stringa, e vengono ordinati i gruppi.</span><span class="sxs-lookup"><span data-stu-id="6abc8-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

<span data-ttu-id="6abc8-110">Per altre informazioni, vedere [Espressioni di query LINQ](../../../linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="6abc8-110">For more information, see [LINQ Query Expressions](../../../linq/index.md).</span></span>

## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="6abc8-111">Variabili tipizzate in modo implicito (var)</span><span class="sxs-lookup"><span data-stu-id="6abc8-111">Implicitly Typed Variables (var)</span></span>

<span data-ttu-id="6abc8-112">Anziché specificare in modo esplicito un tipo quando si dichiara e inizializza una variabile, è possibile usare il modificatore [var](../../../language-reference/keywords/var.md) per indicare al compilatore di dedurre e assegnare il tipo, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6abc8-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

<span data-ttu-id="6abc8-113">Le variabili dichiarate come `var` sono fortemente tipizzate come variabili il cui tipo è specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="6abc8-113">Variables declared as `var` are just as strongly typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="6abc8-114">L'uso di `var` consente di creare tipi anonimi, ma può essere usato solo per variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6abc8-114">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="6abc8-115">Le matrici possono essere dichiarate anche con la tipizzazione implicita.</span><span class="sxs-lookup"><span data-stu-id="6abc8-115">Arrays can also be declared with implicit typing.</span></span>

<span data-ttu-id="6abc8-116">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="6abc8-116">For more information, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

## <a name="object-and-collection-initializers"></a><span data-ttu-id="6abc8-117">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="6abc8-117">Object and Collection Initializers</span></span>

<span data-ttu-id="6abc8-118">Gli inizializzatori di oggetti e Collection consentono di inizializzare gli oggetti senza chiamare in modo esplicito un costruttore per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6abc8-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="6abc8-119">Gli inizializzatori vengono usati in genere nelle espressioni di query quando proiettano i dati di origine in un nuovo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="6abc8-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="6abc8-120">Supponendo di usare una classe denominata `Customer` con le proprietà pubbliche `Name` e `Phone`, l'inizializzatore di oggetto può essere usato come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6abc8-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

<span data-ttu-id="6abc8-121">Continuando con la classe `Customer`, si supponga un'origine dati denominata `IncomingOrders` e che per ogni ordine con `OrderSize` grande si debba creare un nuovo oggetto `Customer` basato sull'ordine.</span><span class="sxs-lookup"><span data-stu-id="6abc8-121">Continuing with our `Customer` class, assume that there is a data source called `IncomingOrders`, and that for each order with a large `OrderSize`, we would like to create a new `Customer` based off of that order.</span></span> <span data-ttu-id="6abc8-122">È possibile eseguire una query LINQ su questa origine dati e usare l'inizializzazione di oggetti per completare una raccolta:</span><span class="sxs-lookup"><span data-stu-id="6abc8-122">A LINQ query can be executed on this data source and use object initialization to fill a collection:</span></span>

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

<span data-ttu-id="6abc8-123">L'origine dati può avere più proprietà in background rispetto alla classe `Customer`, ad esempio `OrderSize`, ma con l'inizializzazione di oggetti i dati restituiti dalla query vengono modellati nel tipo di dati desiderato. Vengono quindi scelti i dati pertinenti per la classe.</span><span class="sxs-lookup"><span data-stu-id="6abc8-123">The data source may have more properties lying under the hood than the `Customer` class such as `OrderSize`, but with object initialization, the data returned from the query is molded into the desired data type; we choose the data that is relevant to our class.</span></span> <span data-ttu-id="6abc8-124">Di conseguenza, è ora disponibile un oggetto `IEnumerable` che contiene i nuovi oggetti `Customer` desiderati.</span><span class="sxs-lookup"><span data-stu-id="6abc8-124">As a result, we now have an `IEnumerable` filled with the new `Customer`s we wanted.</span></span> <span data-ttu-id="6abc8-125">Il codice precedente può anche essere scritto nella sintassi del metodo di LINQ:</span><span class="sxs-lookup"><span data-stu-id="6abc8-125">The above can also be written in LINQ's method syntax:</span></span>

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

<span data-ttu-id="6abc8-126">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="6abc8-126">For more information, see:</span></span>

- [<span data-ttu-id="6abc8-127">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="6abc8-127">Object and Collection Initializers</span></span>](../../classes-and-structs/object-and-collection-initializers.md)

- [<span data-ttu-id="6abc8-128">Sintassi di espressione della query per operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="6abc8-128">Query Expression Syntax for Standard Query Operators</span></span>](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a><span data-ttu-id="6abc8-129">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="6abc8-129">Anonymous Types</span></span>

<span data-ttu-id="6abc8-130">Un tipo anonimo viene costruito dal compilatore e il nome del tipo è disponibile solo al compilatore.</span><span class="sxs-lookup"><span data-stu-id="6abc8-130">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="6abc8-131">I tipi anonimi costituiscono una valida soluzione per raggruppare temporaneamente un set di proprietà nel risultato di una query senza dovere definire un tipo denominato separato.</span><span class="sxs-lookup"><span data-stu-id="6abc8-131">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="6abc8-132">I tipi anonimi vengono inizializzati con una nuova espressione e un inizializzatore di oggetto, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6abc8-132">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

<span data-ttu-id="6abc8-133">Per ulteriori informazioni, vedere [tipi anonimi](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="6abc8-133">For more information, see [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>

## <a name="extension-methods"></a><span data-ttu-id="6abc8-134">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="6abc8-134">Extension Methods</span></span>

<span data-ttu-id="6abc8-135">Un metodo di estensione è un metodo statico che può essere associato a un tipo, in modo da poter essere chiamato come se fosse un metodo di istanza sul tipo.</span><span class="sxs-lookup"><span data-stu-id="6abc8-135">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="6abc8-136">Questa funzionalità consente in pratica di "aggiungere" nuovi metodi ai tipi esistenti senza doverli effettivamente modificare.</span><span class="sxs-lookup"><span data-stu-id="6abc8-136">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="6abc8-137">Gli operatori di query standard sono un set di metodi di estensione che forniscono funzionalità di query LINQ per qualsiasi tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="6abc8-137">The standard query operators are a set of extension methods that provide LINQ query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>

<span data-ttu-id="6abc8-138">Per altre informazioni, vedere [Metodi di estensione](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6abc8-138">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="6abc8-139">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="6abc8-139">Lambda Expressions</span></span>

<span data-ttu-id="6abc8-140">Un'espressione lambda è una funzione inline che usa l'operatore => per separare i parametri di input dal corpo della funzione e, in fase di compilazione, può essere convertita in un delegato o in un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="6abc8-140">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="6abc8-141">Nella programmazione LINQ si verificheranno espressioni lambda quando si eseguono chiamate a metodi diretti agli operatori di query standard.</span><span class="sxs-lookup"><span data-stu-id="6abc8-141">In LINQ programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>

<span data-ttu-id="6abc8-142">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="6abc8-142">For more information, see:</span></span>

- [<span data-ttu-id="6abc8-143">Funzioni anonime</span><span class="sxs-lookup"><span data-stu-id="6abc8-143">Anonymous Functions</span></span>](../../statements-expressions-operators/anonymous-functions.md)

- [<span data-ttu-id="6abc8-144">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="6abc8-144">Lambda Expressions</span></span>](../../statements-expressions-operators/lambda-expressions.md)

- [<span data-ttu-id="6abc8-145">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="6abc8-145">Expression Trees (C#)</span></span>](../expression-trees/index.md)

## <a name="see-also"></a><span data-ttu-id="6abc8-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6abc8-146">See also</span></span>

- [<span data-ttu-id="6abc8-147">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="6abc8-147">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
