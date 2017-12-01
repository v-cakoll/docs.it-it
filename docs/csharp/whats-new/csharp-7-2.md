---
title: "Novità di c# 7.2"
description: "Panoramica delle nuove funzionalità in c# 7.2."
keywords: Progettazione del linguaggio c#, 7.2, Visual Studio 2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a>Novità di c# 7.2

7.2 c# è un altro punto di rilascio che aggiunge il numero di funzionalità utili.
Un tema per questa versione funziona in modo più efficiente con tipi di valore, evitando inutili copie o le allocazioni. 

Le funzionalità rimanenti sono piccole, nice hanno funzionalità.

7.2 c# utilizza il [selezione della lingua versione](csharp-7-1.md#language-version-selection) elemento di configurazione per selezionare la lingua del compilatore.

Le nuove funzionalità del linguaggio in questa versione sono:

* [Semantica di riferimento con tipi di valore](#reference-semantics-with-value-types)
  - Una combinazione di miglioramenti di sintassi che consentono l'utilizzo di tipi di valore utilizzando la semantica di riferimento.
* [Argomenti denominati finali non](#non-trailing-named-arguments)
  - Argomenti denominati possono essere seguiti da argomenti posizionali.
* [Caratteri di sottolineatura iniziali nei valori letterali numerici](#leading-underscores-in-numeric-literals)
  - Valori letterali numerici possono ora includere caratteri di sottolineatura iniziali prima delle cifre stampate.
* [`private protected`modificatore di accesso](#private-protected)
  - Il `private protected` modificatore di accesso consente l'accesso per le classi derivate nello stesso assembly.

## <a name="reference-semantics-with-value-types"></a>Semantica di riferimento con tipi di valore

Funzionalità del linguaggio introdotte in 7.2 consentono di lavorare con i tipi di valore quando si utilizza la semantica di riferimento. Essi sono progettati per migliorare le prestazioni riducendo al minimo la copia tipi di valore senza incorrere nelle allocazioni di memoria associate all'utilizzo di tipi di riferimento. Le funzionalità includono:

 - Il `in` modificatore sui parametri, per specificare che un argomento è passato per riferimento, ma non è stato modificato dal metodo chiamato.
 - Il `ref readonly` modificatore nel metodo restituisce, per indicare che un metodo restituisce il valore per riferimento, ma non consentire la scrittura in quell'oggetto.
 - Il `readonly struct` dichiarazione, per indicare che una struttura non è modificabile e deve essere passata come un `in` parametro ai relativi metodi membro.
 - Il `ref struct` dichiarazione, per indicare che un tipo di struct accede direttamente alla memoria gestita e deve sempre essere stack allocato.

Per ulteriori informazioni su tutte queste modifiche nel [utilizzo di tipi di valore con la semantica di riferimento](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Argomenti denominati finali non

Chiamate al metodo è ora possono utilizzare argomenti denominati che precedono gli argomenti posizionali quando questi argomenti sono nelle posizioni corrette. Per ulteriori informazioni vedere [argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Caratteri di sottolineatura iniziali nei valori letterali numerici

L'implementazione del supporto per i separatori di cifre in c# 7.0 non ha consentito di `_` sia il primo carattere del valore letterale. Esadecimale e valori letterali numerici binari ora possono iniziare con un `_`. 

Ad esempio:

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

Infine, un nuovo modificatore di accesso composta: `private protected` indica che un membro sono accessibili dalle classi derivate che vengono dichiarate nello stesso assembly. Mentre `protected internal` consente l'accesso da classi derivate o le classi che sono nello stesso assembly, `private protected` limita l'accesso ai tipi derivati dichiarato nello stesso assembly.

Per ulteriori informazioni vedere [modificatori di accesso](../language-reference/keywords/access-modifiers.md) nella Guida di riferimento.
