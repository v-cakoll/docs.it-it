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
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a>Creare funzioni definite dall'utente (UDF) in .NET per Apache Spark

Questo articolo illustra come usare le funzioni definite dall'utente in .NET per Apache Spark. Funzioni [UDF)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) sono una funzionalità di Spark che consente di usare funzioni personalizzate per estendere la funzionalità predefinita del sistema. Le funzioni UDF trasformano i valori da una singola riga all'interno di una tabella per produrre un singolo valore di output corrispondente per ogni riga in base alla logica definita nella funzione definita dall'utente.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="define-udfs"></a>Definire UDF

Esaminare la definizione UDF seguente:

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

La funzione definita dall'utente accetta `string` come input il formato di una [colonna](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) di un [dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)e restituisce un oggetto `string` con `hello` accodato davanti all'input.

Il dataframe seguente `df` contiene un elenco di nomi:

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

A questo punto è possibile applicare il precedente definito `udf` al frame di frame `df` :

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

Il seguente dataframe `udfResult` è il risultato della funzione definita dall'utente:

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

Per comprendere meglio come implementare le funzioni definite dall'utente, vedere le [funzioni helper UDF](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) ed [esempi](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) su GitHub.

## <a name="udf-serialization"></a>Serializzazione UDF

Poiché le funzioni definite dall'utente sono funzioni che devono essere eseguite sui thread di lavoro, devono essere serializzate e inviate ai processi di lavoro come parte del payload dal driver. Il [delegato](../../csharp/programming-guide/delegates/index.md), che è un riferimento al metodo, deve essere serializzato e la relativa [destinazione](xref:System.Delegate.Target%2A), ovvero l'istanza della classe in cui il delegato corrente richiama il metodo di istanza. Esaminare questo [esempio di codice in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) per comprendere meglio il modo in cui viene eseguita la serializzazione UDF.

.NET per Apache Spark USA .NET Core, che non supporta la serializzazione dei delegati. Viene invece utilizzata la reflection per serializzare la destinazione in cui è definito il delegato. Quando più delegati sono definiti in un ambito comune, hanno una chiusura condivisa che diventa la destinazione della reflection per la serializzazione.

### <a name="serialization-example"></a>Esempio di serializzazione

Il frammento di codice seguente definisce due variabili stringa a cui viene fatto riferimento in due delegati di funzione che restituiscono le rispettive stringhe come risultato:

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

Il codice C# precedente genera il codice C# Disassembly (Credit Source: [sharplab.io](https://sharplab.io)) seguente dal compilatore:

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

`func`E `func2` condividono la stessa chiusura `<>c__DisplayClass0_0` , ovvero la destinazione serializzata durante la serializzazione dei delegati `func` e `func2` . Anche se `Func<string, string> a` è solo riferimento `s1` , `s2` viene serializzato anche quando i byte vengono inviati ai thread di lavoro.

Questo può causare comportamenti imprevisti in fase di esecuzione (ad esempio, in caso di utilizzo di [variabili broadcast](broadcast-guide.md)), motivo per cui è consigliabile limitare la visibilità delle variabili utilizzate in una funzione all'ambito di tale funzione.

Il frammento di codice seguente è il modo consigliato per implementare il comportamento di serializzazione desiderato:

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

Il codice C# precedente genera il codice C# Disassembly (Credit Source: [sharplab.io](https://sharplab.io)) seguente dal compilatore:

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

Si noti che `func` e `func2` non condividono più una chiusura e hanno rispettivamente le proprie chiusure separate `<>c__DisplayClass0_0` `<>c__DisplayClass0_1` . Quando viene usato come destinazione per la serializzazione, non vengono serializzati elementi diversi dalle variabili a cui viene fatto riferimento per il delegato. Questo comportamento è importante da tenere presente durante l'implementazione di più UDF in un ambito comune.

## <a name="some-spark-udf-caveats"></a>Alcune avvertenze UDF di Spark

* I valori null nelle funzioni definite dall'utente possono generare eccezioni. È responsabilità dello sviluppatore gestirli.
* Le funzioni definite dall'utente non sfruttano le ottimizzazioni fornite dalle funzioni predefinite di Spark, quindi è consigliabile usare le funzioni predefinite, ove possibile.

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Eseguire il debug di un'applicazione .NET per Apache Spark in Windows](debug.md)
