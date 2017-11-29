---
title: Operatori nullable (F#)
description: 'Informazioni sugli operatori ammette valori null che sono disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3108c4ac-9e13-464d-a829-084a6eba038f
ms.openlocfilehash: b3c55dcbfd70c9bcddcc4a990b19a5b92620f822
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="nullable-operators"></a>Operatori nullable

Operatori nullable sono operatori di confronto o aritmetici binari compatibili con i tipi aritmetici nullable su uno o entrambi i lati. Tipi nullable si verificano di frequente quando si lavora con dati provenienti da origini come i database che consentono valori null al posto dei valori effettivi. Operatori nullable vengono spesso utilizzati nelle espressioni di query. Oltre agli operatori ammette valori null per le operazioni aritmetiche e di confronto, è possono utilizzare gli operatori di conversione per la conversione tra tipi nullable. Esistono anche versioni nullable di alcuni operatori di query.


## <a name="table-of-nullable-operators"></a>Tabella degli operatori Nullable
Nella tabella seguente sono elencati gli operatori che ammette valori Null supportati nel linguaggio F #.

|Ammette valori null a sinistra|Ammette valori null a destra|Entrambi i lati ammette valori null|
|---|---|---|
|[?>=](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[>=?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[?>=?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[?>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[?>?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[?<=](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<=?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[?<=?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[?<](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[?<?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[?<>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<>?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[?<>?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>Note
Operatori nullable sono inclusi nel [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) modulo nello spazio dei nomi [spazio](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d). Il tipo di dati ammette valori null è `System.Nullable<'T>`.

Nelle espressioni di query, i tipi nullable si verificano quando si selezionano dati da un'origine dati che ammette valori null anziché i valori. In un database di SQL Server, ogni colonna di dati in una tabella dispone di un attributo che indica se sono consentiti valori null. Se sono consentiti valori null, i dati restituiti dal database possono contenere valori null non può essere rappresentato da un tipo di dati primitivi, ad esempio `int`, `float`e così via. Di conseguenza, i dati vengono restituiti come un `System.Nullable<int>` anziché `int`, e `System.Nullable<float>` anziché `float`. Il valore effettivo può essere ottenuto da un `System.Nullable<'T>` oggetto utilizzando il `Value` , proprietà ed è possibile determinare se un `System.Nullable<'T>` oggetto ha un valore chiamando il `HasValue` metodo. Un altro metodo utile è la `System.Nullable<'T>.GetValueOrDefault` metodo, che consente di ottenere il valore o un valore predefinito del tipo appropriato. Il valore predefinito è una forma di valore "zero", ad esempio 0, 0,0, o `false`.

Tipi nullable possono essere convertiti utilizzando gli operatori di conversione di solito, ad esempio i tipi primitivi non nullable `int` o `float`. È anche possibile eseguire la conversione da un tipo che ammette valori null a un altro tipo che ammette valori null, utilizzare gli operatori di conversione per i tipi nullable. Gli operatori di conversione appropriata hanno lo stesso nome di quelle standard, ma sono in un modulo separato, il [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) modulo il [spazio](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) dello spazio dei nomi. In genere, si apre questo spazio dei nomi quando si lavora con le espressioni di query. In tal caso, è possibile utilizzare gli operatori di conversione che ammette valori null aggiungendo il prefisso `Nullable.` all'operatore di conversione appropriate, come illustrato nel codice seguente.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

L'output è `10.000000`.

Query nei campi di dati ammette valori null, ad esempio `sumByNullable`, esiste anche per l'utilizzo nelle espressioni di query. Gli operatori di query per i tipi che non ammette valori null non sono compatibili con tipo con i tipi nullable, è necessario utilizzare la versione dell'operatore di query appropriata che ammette valori null quando si lavora con valori di dati ammette valori null. Per ulteriori informazioni, vedere [espressioni di Query](../query-expressions.md).

Nell'esempio seguente viene illustrato l'utilizzo degli operatori che ammette valori null in un'espressione di query F #. La prima query viene illustrato come scrivere una query senza un operatore che ammette valori null. la seconda query viene illustrata una query equivalente che utilizza un operatore che ammette valori null. Per il contesto completo, incluso come configurare il database per utilizzare il codice di esempio, vedere [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](../../tutorials/type-providers/accessing-a-sql-database.md).

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a>Vedere anche

[Provider di tipi](../../tutorials/type-providers/index.md)

[Espressioni di query](../query-expressions.md)
