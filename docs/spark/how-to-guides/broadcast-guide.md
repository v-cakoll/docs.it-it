---
title: Usare le variabili broadcast in .NET per Apache Spark
description: Informazioni su come usare le variabili broadcast in .NET per Apache Spark applicazioni.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 391e32cda14a9b3186ac96800351ddcb39a3d359
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105606"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a><span data-ttu-id="e3d6b-103">Usare le variabili broadcast in .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e3d6b-103">Use broadcast variables in .NET for Apache Spark</span></span>

<span data-ttu-id="e3d6b-104">Questo articolo illustra come usare le variabili broadcast in .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-104">In this article, you learn how to use broadcast variables in .NET for Apache Spark.</span></span> <span data-ttu-id="e3d6b-105">Le [variabili broadcast in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) sono meccanismi per la condivisione di variabili tra esecutori destinati a essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-105">[Broadcast variables in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) are mechanisms for sharing variables across executors that are meant to be read-only.</span></span> <span data-ttu-id="e3d6b-106">Le variabili broadcast consentono di memorizzare nella cache una variabile di sola lettura in ogni computer invece di inviarne una copia con le attività.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-106">Broadcast variables allow you to keep a read-only variable cached on each machine rather than shipping a copy of it with tasks.</span></span> <span data-ttu-id="e3d6b-107">È possibile usare le variabili broadcast per assegnare a ogni nodo una copia di un set di dati di input di grandi dimensioni in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-107">You can use broadcast variables to give every node a copy of a large input dataset in an efficient manner.</span></span>

<span data-ttu-id="e3d6b-108">Poiché i dati vengono inviati una sola volta, le variabili broadcast presentano vantaggi a livello di prestazioni rispetto alle variabili locali che vengono spedite agli esecutori con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-108">Because the data is sent only once, broadcast variables have performance benefits when compared to local variables that are shipped to the executors with each task.</span></span> <span data-ttu-id="e3d6b-109">Vedere la [documentazione ufficiale della variabile broadcast](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) per comprendere meglio le variabili di broadcast e il motivo per cui vengono usate.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-109">Refer to the [official broadcast variable documentation](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) to get a deeper understanding of broadcast variables and why they are used.</span></span>

## <a name="create-broadcast-variables"></a><span data-ttu-id="e3d6b-110">Creare variabili broadcast</span><span class="sxs-lookup"><span data-stu-id="e3d6b-110">Create broadcast variables</span></span>

<span data-ttu-id="e3d6b-111">Per creare una variabile broadcast, chiamare `SparkContext.Broadcast(v)` per qualsiasi variabile `v` .</span><span class="sxs-lookup"><span data-stu-id="e3d6b-111">To create a broadcast variable, call `SparkContext.Broadcast(v)` for any variable `v`.</span></span> <span data-ttu-id="e3d6b-112">La variabile broadcast è un wrapper per la variabile `v` e il relativo valore può essere accessibile chiamando il `Value()` metodo.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-112">The broadcast variable is a wrapper around the variable `v`, and its value can be accessed by calling the `Value()` method.</span></span>

<span data-ttu-id="e3d6b-113">Nel frammento di codice seguente viene creata una variabile di stringa `v` e viene creata una variabile di broadcast `bv` quando `SparkContext.Broadcast(v)` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-113">In the following code snippet, a string variable `v` is created, and a broadcast variable `bv` is created when `SparkContext.Broadcast(v)`is called.</span></span> <span data-ttu-id="e3d6b-114">Si noti che il parametro di tipo per `Broadcast` , String, corrisponde al tipo della variabile da trasmettere.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-114">Notice the type parameter for `Broadcast`, string, matches the type of the variable being broadcasted.</span></span> <span data-ttu-id="e3d6b-115">La funzione definita dall'utente (UDF) restituisce il valore di `bv` .</span><span class="sxs-lookup"><span data-stu-id="e3d6b-115">The user-defined function (UDF) returns the value of `bv`.</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a><span data-ttu-id="e3d6b-116">Elimina variabili broadcast</span><span class="sxs-lookup"><span data-stu-id="e3d6b-116">Delete broadcast variables</span></span>

<span data-ttu-id="e3d6b-117">La variabile broadcast può essere eliminata da tutti gli esecutori chiamando il `Destroy()` metodo.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-117">The broadcast variable can be deleted from all executors by calling the `Destroy()` method.</span></span>

```csharp
bv.Destroy();
```

<span data-ttu-id="e3d6b-118">`Destroy()`Elimina tutti i dati e i metadati correlati alla variabile broadcast e deve essere utilizzato con cautela.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-118">`Destroy()` deletes all data and metadata related to the broadcast variable and should be used with caution.</span></span> <span data-ttu-id="e3d6b-119">Una volta distrutta, una variabile di broadcast non può essere riutilizzata.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-119">Once a broadcast variable is destroyed, it can't be used again.</span></span>

## <a name="limit-broadcast-variable-scope-in-udfs"></a><span data-ttu-id="e3d6b-120">Limitare l'ambito della variabile broadcast nelle UDF</span><span class="sxs-lookup"><span data-stu-id="e3d6b-120">Limit broadcast variable scope in UDFs</span></span>

<span data-ttu-id="e3d6b-121">Quando si usano le variabili broadcast nelle UDF, è necessario limitare l'ambito della variabile solo alla funzione definita dall'utente che fa riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-121">When you use broadcast variables in UDFs, you need to limit the scope of the variable to only the UDF that is referencing the variable.</span></span> <span data-ttu-id="e3d6b-122">La [Guida all'uso di UDF](udf-guide.md) descrive questo fenomeno in modo dettagliato.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-122">The [guide to using UDFs](udf-guide.md) describes this phenomenon in detail.</span></span> <span data-ttu-id="e3d6b-123">L'ambito è particolarmente importante quando si chiama `Destroy()` sulla variabile broadcast.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-123">Scope is especially crucial when you call `Destroy()` on the broadcast variable.</span></span>

<span data-ttu-id="e3d6b-124">Se la variabile di broadcast distrutta è visibile o accessibile da altre UDF, viene prelevata per la serializzazione da parte di tutte le funzioni definite dall'utente, anche se non vi viene fatto riferimento da tali funzioni.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-124">If the broadcast variable that has been destroyed is visible to or accessible from other UDFs, it gets picked up for serialization by all of the UDFs, even if it is not being referenced by them.</span></span> <span data-ttu-id="e3d6b-125">.NET per Apache Spark non è in grado di serializzare la variabile di broadcast distrutta, generando un errore.</span><span class="sxs-lookup"><span data-stu-id="e3d6b-125">.NET for Apache Spark is unable to serialize the destroyed broadcast variable, which results in an error.</span></span> <span data-ttu-id="e3d6b-126">Il frammento di codice seguente illustra questo errore:</span><span class="sxs-lookup"><span data-stu-id="e3d6b-126">The following code snippet demonstrates this error:</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

// Using the broadcast variable in a UDF:
Func<Column, Column> udf1 = Udf<string, string>(
    str => $"{str}: {bv.Value()}");

// Destroying bv
bv.Destroy();

// Calling udf1 after destroying bv throws the following expected exception:
// org.apache.spark.SparkException: Attempted to use Broadcast(0) after it was destroyed
df.Select(udf1(df["_1"])).Show();

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 throws the following (unexpected) exception:
// [Error] [JvmBridge] org.apache.spark.SparkException: Task not serializable
df.Select(udf2(df["_1"])).Show();
```

<span data-ttu-id="e3d6b-127">Il frammento di codice seguente illustra come garantire che l'eliminazione `bv` non abbia effetto a `udf2` causa di un comportamento di serializzazione imprevisto:</span><span class="sxs-lookup"><span data-stu-id="e3d6b-127">The following code snippet demonstrates how to ensure that destroying `bv` doesn't affect `udf2` because of an unexpected serialization behavior:</span></span>

```csharp
string v = "Variable to be broadcasted";
// Restricting the visibility of bv to only the UDF referencing it
{
    Broadcast<string> bv = SparkContext.Broadcast(v);

    // Using the broadcast variable in a UDF:
    Func<Column, Column> udf1 = Udf<string, string>(
        str => $"{str}: {bv.Value()}");

    // Destroying bv
    bv.Destroy();
}

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 works fine as expected
df.Select(udf2(df["_1"])).Show();
```

## <a name="next-steps"></a><span data-ttu-id="e3d6b-128">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e3d6b-128">Next steps</span></span>

* [<span data-ttu-id="e3d6b-129">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="e3d6b-129">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="e3d6b-130">Eseguire il debug di un'applicazione .NET per Apache Spark in Windows</span><span class="sxs-lookup"><span data-stu-id="e3d6b-130">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
* [<span data-ttu-id="e3d6b-131">Distribuire .NET per Apache Spark Worker e i file binari delle funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e3d6b-131">Deploy .NET for Apache Spark worker and user-defined function binaries</span></span>](deploy-worker-udf-binaries.md)
