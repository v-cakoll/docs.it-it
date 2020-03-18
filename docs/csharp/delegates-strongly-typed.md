---
title: Delegati fortemente tipizzati
description: Informazioni su come usare i tipi delegati generici per dichiarare tipi personalizzati quando si crea una funzionalità che richiede i delegati.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 798e8b597389bc99d10e587ec417a4e717f28abc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146203"
---
# <a name="strongly-typed-delegates"></a>Delegati fortemente tipizzati

[Indietro](delegate-class.md)

Nell'articolo precedente è stata descritta la creazione di tipi di delegato specifici tramite la parola chiave `delegate`.

La classe Delegate astratta offre l'infrastruttura per l'accoppiamento libero e la chiamata. I tipi delegati concreti diventano più utili includendo e imponendo l'indipendenza dai tipi per i metodi aggiunti all'elenco di chiamate per un oggetto delegato. Quando si usa la parola chiave `delegate` e si definisce un tipo delegato concreto, il compilatore genera tali metodi.

In pratica, verranno creati nuovi tipi delegati ogni volta che è necessaria una firma del metodo diversa. Questa operazione potrebbe risultare tediosa dopo un periodo di tempo. Ogni nuova funzionalità richiede nuovi tipi delegati.

Fortunatamente, questo non è necessario. Il framework .NET Core include diversi tipi che è possibile riutilizzare quando sono necessari tipi delegati. Poiché si tratta di definizioni [generiche](programming-guide/generics/index.md) è possibile dichiarare personalizzazioni quando sono necessarie nuove dichiarazioni di metodi.

Il primo di questi tipi è il tipo <xref:System.Action> e diverse variazioni:

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

Il modificatore `in` nell'argomento di tipo generico è descritto nell'articolo sulla covarianza.

Sono disponibili variazioni del delegato `Action` che contengono fino a 16 argomenti, ad esempio <xref:System.Action%6016>.
È importante che queste definizioni usino argomenti generici diversi per ogni argomento di delegato in modo da offrire la massima flessibilità. Gli argomenti del metodo possono essere dello stesso tipo, ma non devono esserlo necessariamente.

Usare uno dei tipi `Action` per ogni tipo delegato con tipo restituito void.

Il framework include anche diversi tipi delegati generici che è possibile usare per i tipi delegati che restituiscono valori:

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

Il modificatore `out` nell'argomento di tipo generico del risultato è descritto nell'articolo sulla covarianza.

Sono disponibili variazioni del delegato `Func` che contengono fino a 16 argomenti di input, ad esempio <xref:System.Func%6017>.
Per convenzione, il tipo del risultato è sempre l'ultimo parametro di tipo in tutte le dichiarazioni `Func`.

Usare uno dei tipi `Func` per ogni tipo delegato che restituisce un valore.

C'è anche un specializzato<xref:System.Predicate%601>
tipo per un delegato che restituisce un test su un singolo valore:

```csharp
public delegate bool Predicate<in T>(T obj);
```

È possibile notare che per ogni tipo `Predicate`, esiste un tipo `Func` strutturalmente equivalente, ad esempio:

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

Si potrebbe pensare che questi due tipi siano equivalenti. Ma non lo sono.
Queste due variabili non possono essere usate indifferentemente. A una variabile di un tipo non è possibile assegnare un altro tipo. Il sistema dei tipi di C# usa i nomi dei tipi definiti, non la struttura.

Tutte queste definizioni di tipi delegati nella libreria .NET Core dovrebbero eliminare la necessità di definire un nuovo tipo delegato per ogni nuova funzionalità creata che richiede delegati. Queste definizioni generiche dovrebbero offrire tutti i tipi delegati necessari nella maggior parte delle situazioni. È possibile creare semplicemente un'istanza di uno di questi tipi con i parametri di tipo richiesti. Nel caso di algoritmi che possono essere definiti come generici, questi delegati possono essere usati come tipi generici.

Ciò dovrebbe consentire di risparmiare tempo e di ridurre il numero di nuovi tipi da creare per usare i delegati.

Nel articolo successivo sono descritti diversi modelli comuni per l'uso pratico dei delegati.

[Avanti](delegates-patterns.md)
