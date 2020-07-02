---
title: Usare le variabili broadcast in .NET per Apache Spark
description: Informazioni su come usare le variabili broadcast in .NET per Apache Spark applicazioni.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: d86b160855cc4d3f3a6502f5606d4766b7c06aa0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617856"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a>Usare le variabili broadcast in .NET per Apache Spark

Questo articolo illustra come usare le variabili broadcast in .NET per Apache Spark. Le [variabili broadcast in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) sono meccanismi per la condivisione di variabili tra esecutori destinati a essere di sola lettura. Le variabili broadcast consentono di memorizzare nella cache una variabile di sola lettura in ogni computer invece di inviarne una copia con le attività. È possibile usare le variabili broadcast per assegnare a ogni nodo una copia di un set di dati di input di grandi dimensioni in modo efficiente.

Poiché i dati vengono inviati una sola volta, le variabili broadcast presentano vantaggi a livello di prestazioni rispetto alle variabili locali che vengono spedite agli esecutori con ogni attività. Vedere la [documentazione ufficiale della variabile broadcast](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) per comprendere meglio le variabili di broadcast e il motivo per cui vengono usate.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="create-broadcast-variables"></a>Creare variabili broadcast

Per creare una variabile broadcast, chiamare `SparkContext.Broadcast(v)` per qualsiasi variabile `v` . La variabile broadcast è un wrapper per la variabile `v` e il relativo valore può essere accessibile chiamando il `Value()` metodo.

Nel frammento di codice seguente viene creata una variabile di stringa `v` e viene creata una variabile di broadcast `bv` quando `SparkContext.Broadcast(v)` viene chiamato il metodo. Si noti che il parametro di tipo per `Broadcast` , String, corrisponde al tipo della variabile da trasmettere. La funzione definita dall'utente (UDF) restituisce il valore di `bv` .

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a>Elimina variabili broadcast

La variabile broadcast può essere eliminata da tutti gli esecutori chiamando il `Destroy()` metodo.

```csharp
bv.Destroy();
```

`Destroy()`Elimina tutti i dati e i metadati correlati alla variabile broadcast e deve essere utilizzato con cautela. Una volta distrutta, una variabile di broadcast non può essere riutilizzata.

## <a name="limit-broadcast-variable-scope-in-udfs"></a>Limitare l'ambito della variabile broadcast nelle UDF

Quando si usano le variabili broadcast nelle UDF, è necessario limitare l'ambito della variabile solo alla funzione definita dall'utente che fa riferimento alla variabile. La [Guida all'uso di UDF](udf-guide.md) descrive questo fenomeno in modo dettagliato. L'ambito è particolarmente importante quando si chiama `Destroy()` sulla variabile broadcast.

Se la variabile di broadcast distrutta è visibile o accessibile da altre UDF, viene prelevata per la serializzazione da parte di tutte le funzioni definite dall'utente, anche se non vi viene fatto riferimento da tali funzioni. .NET per Apache Spark non è in grado di serializzare la variabile di broadcast distrutta, generando un errore. Il frammento di codice seguente illustra questo errore:

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

Il frammento di codice seguente illustra come garantire che l'eliminazione `bv` non abbia effetto a `udf2` causa di un comportamento di serializzazione imprevisto:

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

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Eseguire il debug di un'applicazione .NET per Apache Spark in Windows](debug.md)
* [Distribuire .NET per Apache Spark Worker e i file binari delle funzioni definite dall'utente](deploy-worker-udf-binaries.md)
