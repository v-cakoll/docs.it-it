---
title: Funzionalità di C# che supportano LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 9fc8adaa49d02f8b69c2db6e94a28b9fab36b3b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635795"
---
# <a name="c-features-that-support-linq"></a>Funzionalità di C# che supportano LINQ

Nella sezione seguente vengono illustrati i nuovi costrutti di linguaggio introdotti in C# 3.0. Anche se queste nuove funzionalità vengono tutte utilizzate in una certa misura con le query LINQLINQ, non sono limitate a LINQ e possono essere utilizzate in qualsiasi contesto in cui sono utili.

## <a name="query-expressions"></a>Espressioni di query

Le espressioni di query usano una sintassi dichiarativa simile a SQL o XQuery per eseguire una query sulle raccolte IEnumerable. In fase di compilazione la sintassi della query viene convertita in chiamate al metodo nell'implementazione di un provider LINQ dei metodi di estensione dell'operatore di query standard. Le applicazioni controllano gli operatori di query standard inclusi nell'ambito specificando lo spazio dei nomi adatto con una direttiva `using`. Nell'espressione di query seguente viene usata una matrice di stringhe, raggruppate in base al primo carattere della stringa, e vengono ordinati i gruppi.

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

Per altre informazioni, vedere [Espressioni di query LINQ](../../../linq/index.md).

## <a name="implicitly-typed-variables-var"></a>Variabili tipizzate in modo implicito (var)

Anziché specificare in modo esplicito un tipo quando si dichiara e inizializza una variabile, è possibile usare il modificatore [var](../../../language-reference/keywords/var.md) per indicare al compilatore di dedurre e assegnare il tipo, come illustrato di seguito:

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

Le variabili dichiarate come `var` sono fortemente tipizzate esattamente come le variabili in cui il tipo viene specificato in modo esplicito. L'uso di `var` consente di creare tipi anonimi, ma può essere usato solo per variabili locali. Le matrici possono essere dichiarate anche con la tipizzazione implicita.

Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../classes-and-structs/implicitly-typed-local-variables.md).

## <a name="object-and-collection-initializers"></a>Inizializzatori di oggetto e di raccolta

Gli inizializzatori di oggetti e Collection consentono di inizializzare gli oggetti senza chiamare in modo esplicito un costruttore per l'oggetto. Gli inizializzatori vengono usati in genere nelle espressioni di query quando proiettano i dati di origine in un nuovo tipo di dati. Supponendo di usare una classe denominata `Customer` con le proprietà pubbliche `Name` e `Phone`, l'inizializzatore di oggetto può essere usato come nel codice seguente:

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

Continuando con la classe `Customer`, si supponga un'origine dati denominata `IncomingOrders` e che per ogni ordine con `OrderSize` grande si debba creare un nuovo oggetto `Customer` basato sull'ordine. È possibile eseguire una query LINQ su questa origine dati e usare l'inizializzazione di oggetti per completare una raccolta:

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

L'origine dati può avere più proprietà in background rispetto alla classe `Customer`, ad esempio `OrderSize`, ma con l'inizializzazione di oggetti i dati restituiti dalla query vengono modellati nel tipo di dati desiderato. Vengono quindi scelti i dati pertinenti per la classe. Di conseguenza, è ora disponibile un oggetto `IEnumerable` che contiene i nuovi oggetti `Customer` desiderati. Il codice precedente può anche essere scritto nella sintassi del metodo di LINQ:

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

Per altre informazioni, vedere:

- [Inizializzatori di oggetto e di raccoltaObject and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md)

- [Sintassi di espressione della query per operatori di query standard](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a>Tipi anonimi

Un tipo anonimo viene costruito dal compilatore e il nome del tipo è disponibile solo al compilatore. I tipi anonimi costituiscono una valida soluzione per raggruppare temporaneamente un set di proprietà nel risultato di una query senza dovere definire un tipo denominato separato. I tipi anonimi vengono inizializzati con una nuova espressione e un inizializzatore di oggetto, come illustrato di seguito:

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

Per ulteriori informazioni, vedere [Tipi anonimi](../../classes-and-structs/anonymous-types.md).

## <a name="extension-methods"></a>Metodi di estensione

Un metodo di estensione è un metodo statico che può essere associato a un tipo, in modo da poter essere chiamato come se fosse un metodo di istanza sul tipo. Questa funzionalità consente in pratica di "aggiungere" nuovi metodi ai tipi esistenti senza doverli effettivamente modificare. Gli operatori di query standard sono un set di metodi <xref:System.Collections.Generic.IEnumerable%601>di estensione che forniscono funzionalità di query LINQ per qualsiasi tipo che implementa .

Per altre informazioni, vedere [Metodi di estensione](../../classes-and-structs/extension-methods.md).

## <a name="lambda-expressions"></a>Espressioni lambda

Un'espressione lambda è una funzione inline che usa l'operatore => per separare i parametri di input dal corpo della funzione e, in fase di compilazione, può essere convertita in un delegato o in un albero delle espressioni. Nella programmazione LINQLINQ, si incontreranno espressioni lambda quando si effettuano chiamate dirette al metodo per gli operatori di query standard.

Per altre informazioni, vedere:

- [Funzioni anonime](../../statements-expressions-operators/anonymous-functions.md)

- [Espressioni lambdaLambda Expressions](../../statements-expressions-operators/lambda-expressions.md)

- [Alberi delle espressioni (C#)](../expression-trees/index.md)

## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (C#)](./index.md)
