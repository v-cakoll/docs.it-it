---
title: Creare funzioni definite dall'utente (UDF) in .NET per Apache Spark
description: Informazioni su come implementare funzioni definite dall'utente (UDF) in .NET per Apache Spark applicazioni.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 97afda8ed17d3719c534d72ad3ad026745a70922
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620924"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a><span data-ttu-id="0c7e6-103">Creare funzioni definite dall'utente (UDF) in .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0c7e6-103">Create user-defined functions (UDF) in .NET for Apache Spark</span></span>

<span data-ttu-id="0c7e6-104">Questo articolo illustra come usare le funzioni definite dall'utente in .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-104">In this article, you learn how to use user-defined functions (UDF) in .NET for Apache Spark.</span></span> <span data-ttu-id="0c7e6-105">Funzioni [UDF)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) sono una funzionalità di Spark che consente di usare funzioni personalizzate per estendere la funzionalità predefinita del sistema.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-105">[UDFs)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) are a Spark feature that allow you to use custom functions to extend the system's built-in functionality.</span></span> <span data-ttu-id="0c7e6-106">Le funzioni UDF trasformano i valori da una singola riga all'interno di una tabella per produrre un singolo valore di output corrispondente per ogni riga in base alla logica definita nella funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-106">UDFs transform values from a single row within a table to produce a single corresponding output value per row based on the logic defined in the UDF.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="define-udfs"></a><span data-ttu-id="0c7e6-107">Definire UDF</span><span class="sxs-lookup"><span data-stu-id="0c7e6-107">Define UDFs</span></span>

<span data-ttu-id="0c7e6-108">Esaminare la definizione UDF seguente:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-108">Review the following UDF definition:</span></span>

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

<span data-ttu-id="0c7e6-109">La funzione definita dall'utente accetta `string` come input il formato di una [colonna](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) di un [dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)e restituisce un oggetto `string` con `hello` accodato davanti all'input.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-109">The UDF takes a `string` as an input in the form of a [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) of a [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) and returns a `string` with `hello` appended in front of the input.</span></span>

<span data-ttu-id="0c7e6-110">Il dataframe seguente `df` contiene un elenco di nomi:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-110">The following DataFrame `df` contains a list of names:</span></span>

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

<span data-ttu-id="0c7e6-111">A questo punto è possibile applicare il precedente definito `udf` al frame di frame `df` :</span><span class="sxs-lookup"><span data-stu-id="0c7e6-111">Now let's apply the above defined `udf` to the DataFrame `df`:</span></span>

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

<span data-ttu-id="0c7e6-112">Il seguente dataframe `udfResult` è il risultato della funzione definita dall'utente:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-112">The following DataFrame `udfResult` is the result of the UDF:</span></span>

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

<span data-ttu-id="0c7e6-113">Per comprendere meglio come implementare le funzioni definite dall'utente, vedere le [funzioni helper UDF](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) ed [esempi](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-113">To better understand how to implement UDFs, review the [UDF helper functions](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) and [examples](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) on GitHub.</span></span>

## <a name="udf-serialization"></a><span data-ttu-id="0c7e6-114">Serializzazione UDF</span><span class="sxs-lookup"><span data-stu-id="0c7e6-114">UDF serialization</span></span>

<span data-ttu-id="0c7e6-115">Poiché le funzioni definite dall'utente sono funzioni che devono essere eseguite sui thread di lavoro, devono essere serializzate e inviate ai processi di lavoro come parte del payload dal driver.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-115">Because UDFs are functions that need to be executed on workers, they have to be serialized and sent to the workers as part of the payload from the driver.</span></span> <span data-ttu-id="0c7e6-116">Il [delegato](../../csharp/programming-guide/delegates/index.md), che è un riferimento al metodo, deve essere serializzato e la relativa [destinazione](xref:System.Delegate.Target%2A), ovvero l'istanza della classe in cui il delegato corrente richiama il metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-116">The [delegate](../../csharp/programming-guide/delegates/index.md), which is a reference to the method, needs to be serialized as well as its [target](xref:System.Delegate.Target%2A), which is the class instance on which the current delegate invokes the instance method.</span></span> <span data-ttu-id="0c7e6-117">Esaminare questo [esempio di codice in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) per comprendere meglio il modo in cui viene eseguita la serializzazione UDF.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-117">Review this [code example in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) to get a better understanding of how UDF serialization is being done.</span></span>

<span data-ttu-id="0c7e6-118">.NET per Apache Spark USA .NET Core, che non supporta la serializzazione dei delegati.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-118">.NET for Apache Spark uses .NET Core, which doesn't support serializing delegates.</span></span> <span data-ttu-id="0c7e6-119">Viene invece utilizzata la reflection per serializzare la destinazione in cui è definito il delegato.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-119">Instead, reflection is used to serialize the target where the delegate is defined.</span></span> <span data-ttu-id="0c7e6-120">Quando più delegati sono definiti in un ambito comune, hanno una chiusura condivisa che diventa la destinazione della reflection per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-120">When multiple delegates are defined in a common scope, they have a shared closure that becomes the target of reflection for serialization.</span></span>

### <a name="serialization-example"></a><span data-ttu-id="0c7e6-121">Esempio di serializzazione</span><span class="sxs-lookup"><span data-stu-id="0c7e6-121">Serialization example</span></span>

<span data-ttu-id="0c7e6-122">Il frammento di codice seguente definisce due variabili stringa a cui viene fatto riferimento in due delegati di funzione che restituiscono le rispettive stringhe come risultato:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-122">The following code snippet defines two string variables that are being referenced in two function delegates that return the respective strings as a result:</span></span>

```csharp
using System;

public class C {
    public void M() {
        string s1 = "s1";
        string s2 = "s2";
        Func<string, string> a = str => s1;
        Func<string, string> b = str => s2;
    }
}
```

<span data-ttu-id="0c7e6-123">Il codice C# precedente genera il codice C# Disassembly (Credit Source: [sharplab.io](https://sharplab.io)) seguente dal compilatore:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-123">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        public string s2;

        internal string <M>b__0(string str)
        {
            return s1;
        }

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        <>c__DisplayClass0_.s2 = "s2";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_.<M>b__1);
    }
}
```

<span data-ttu-id="0c7e6-124">`func`E `func2` condividono la stessa chiusura `<>c__DisplayClass0_0` , ovvero la destinazione serializzata durante la serializzazione dei delegati `func` e `func2` .</span><span class="sxs-lookup"><span data-stu-id="0c7e6-124">Both `func` and `func2` share the same closure `<>c__DisplayClass0_0`, which is the target that is serialized when serializing the delegates `func` and `func2`.</span></span> <span data-ttu-id="0c7e6-125">Anche se `Func<string, string> a` è solo riferimento `s1` , `s2` viene serializzato anche quando i byte vengono inviati ai thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-125">Even though `Func<string, string> a` is only referencing `s1`, `s2` is also serialized when the bytes are sent to the workers.</span></span>

<span data-ttu-id="0c7e6-126">Questo può causare comportamenti imprevisti in fase di esecuzione (ad esempio, in caso di utilizzo di [variabili broadcast](broadcast-guide.md)), motivo per cui è consigliabile limitare la visibilità delle variabili utilizzate in una funzione all'ambito di tale funzione.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-126">This can lead to some unexpected behaviors at runtime (like in the case of using [broadcast variables](broadcast-guide.md)), which is why we recommend that you restrict the visibility of the variables used in a function to that function's scope.</span></span>

<span data-ttu-id="0c7e6-127">Il frammento di codice seguente è il modo consigliato per implementare il comportamento di serializzazione desiderato:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-127">The following code snippet is the recommended way to implement the desired serialization behavior:</span></span>

```csharp
using System;

public class C {
    public void M() {
        {
            string s1 = "s1";
            Func<string, string> a = str => s1;
        }
        {
            string s2 = "s2";
            Func<string, string> b = str => s2;
        }
    }
}
```

<span data-ttu-id="0c7e6-128">Il codice C# precedente genera il codice C# Disassembly (Credit Source: [sharplab.io](https://sharplab.io)) seguente dal compilatore:</span><span class="sxs-lookup"><span data-stu-id="0c7e6-128">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        internal string <M>b__0(string str)
        {
            return s1;
        }
    }

    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_1
    {
        public string s2;

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        <>c__DisplayClass0_1 <>c__DisplayClass0_2 = new <>c__DisplayClass0_1();
        <>c__DisplayClass0_2.s2 = "s2";
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_2.<M>b__1);
    }
}
```

<span data-ttu-id="0c7e6-129">Si noti che `func` e `func2` non condividono più una chiusura e hanno rispettivamente le proprie chiusure separate `<>c__DisplayClass0_0` `<>c__DisplayClass0_1` .</span><span class="sxs-lookup"><span data-stu-id="0c7e6-129">Notice that `func` and `func2` no longer share a closure, and they have their own separate closures `<>c__DisplayClass0_0` and `<>c__DisplayClass0_1` respectively.</span></span> <span data-ttu-id="0c7e6-130">Quando viene usato come destinazione per la serializzazione, non vengono serializzati elementi diversi dalle variabili a cui viene fatto riferimento per il delegato.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-130">When used as the target for serialization, nothing other than the referenced variables will get serialized for the delegate.</span></span> <span data-ttu-id="0c7e6-131">Questo comportamento è importante da tenere presente durante l'implementazione di più UDF in un ambito comune.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-131">This behavior is important to keep in mind while implementing multiple UDFs in a common scope.</span></span>

## <a name="some-spark-udf-caveats"></a><span data-ttu-id="0c7e6-132">Alcune avvertenze UDF di Spark</span><span class="sxs-lookup"><span data-stu-id="0c7e6-132">Some Spark UDF caveats</span></span>

* <span data-ttu-id="0c7e6-133">I valori null nelle funzioni definite dall'utente possono generare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-133">Null values in UDFs can throw exceptions.</span></span> <span data-ttu-id="0c7e6-134">È responsabilità dello sviluppatore gestirli.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-134">It's the responsibility of the developer to handle them.</span></span>
* <span data-ttu-id="0c7e6-135">Le funzioni definite dall'utente non sfruttano le ottimizzazioni fornite dalle funzioni predefinite di Spark, quindi è consigliabile usare le funzioni predefinite, ove possibile.</span><span class="sxs-lookup"><span data-stu-id="0c7e6-135">UDFs don't leverage the optimizations provided by Spark's built-in functions, so it's recommended to use built-in functions where possible.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c7e6-136">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0c7e6-136">Next steps</span></span>

* [<span data-ttu-id="0c7e6-137">Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0c7e6-137">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="0c7e6-138">Eseguire il debug di un'applicazione .NET per Apache Spark in Windows</span><span class="sxs-lookup"><span data-stu-id="0c7e6-138">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
