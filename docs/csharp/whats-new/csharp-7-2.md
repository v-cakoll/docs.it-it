---
title: Novità di C# 7.2
description: Panoramica delle nuove funzionalità in C# 7.2.
ms.date: 08/16/2017
ms.openlocfilehash: b813bf5b38ef17986b21e928c9c86e583174c7d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-72"></a>Novità di C# 7.2

C# 7.2 è un'altra Point Release che aggiunge numerose funzionalità utili.
Il tema centrale di questa versione è l'uso più efficiente dei tipi valore, evitando inutili copie o allocazioni. 

Le funzionalità rimanenti sono piccole e utili.

C# 7.2 usa l'elemento di configurazione per la [selezione della versione del linguaggio](csharp-7-1.md#language-version-selection) per selezionare la versione del linguaggio del compilatore.

Le nuove funzionalità relative al linguaggio in questa versione sono:

* [Semantica di riferimento con i tipi valore](#reference-semantics-with-value-types)
  - Una combinazione di miglioramenti della sintassi che consentono l'utilizzo dei tipi valore tramite la semantica di riferimento.
* [Argomenti denominati non finali](#non-trailing-named-arguments)
  - Gli argomenti denominati possono essere seguiti da argomenti posizionali.
* [Caratteri di sottolineatura iniziali nei valori letterali numerici](#leading-underscores-in-numeric-literals)
  - I valori letterali numerici possono ora includere caratteri di sottolineatura iniziali prima di qualsiasi cifra stampata.
* [Modificatore di accesso `private protected`](#private-protected-access-modifier)
  - Il modificatore di accesso `private protected` consente l'accesso per le classi derivate nello stesso assembly.

## <a name="reference-semantics-with-value-types"></a>Semantica di riferimento con i tipi valore

Le funzionalità del linguaggio introdotte nella versione 7.2 consentono di lavorare con i tipi valore usando allo stesso tempo la semantica di riferimento. Queste funzionalità sono state progettate per migliorare le prestazioni riducendo al minimo la copia dei tipi valore senza dover sostenere le allocazioni di memoria associate all'uso dei tipi riferimento. Sono incluse le funzionalità seguenti:

 - Il modificatore `in` per i parametri, per specificare che un argomento viene passato per riferimento, ma non modificato dal metodo chiamato.
 - Il modificatore `ref readonly` per i valori restituiti dai metodi, per indicare che un metodo restituisce il valore per riferimento, ma non consente scritture su tale oggetto.
 - La dichiarazione `readonly struct` per indicare che uno struct non è modificabile e deve essere passato come parametro `in` ai relativi metodi membro.
 - La dichiarazione `ref struct` per indicare che un tipo di struct accede direttamente alla memoria gestita e deve sempre essere allocato nello stack.

Per altre informazioni su tutte queste modifiche, vedere [Semantica di riferimento con tipi di valore](../reference-semantics-with-value-types.md).

## <a name="non-trailing-named-arguments"></a>Argomenti denominati non finali

Per le chiamate di metodi è ora possibile usare argomenti denominati che precedono gli argomenti posizionali quando questi argomenti denominati sono nelle posizioni corrette. Per altre informazioni, vedere [Argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Caratteri di sottolineatura iniziali nei valori letterali numerici

L'implementazione del supporto per i separatori di cifre in C# 7.0 non consentiva l'uso di `_` come primo carattere del valore letterale. I valori letterali numerici esadecimali e binari possono ora iniziare con `_`. 

Ad esempio:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Modificatore di accesso _private protected_

Infine, il nuovo modificatore di accesso composto `private protected` indica che un membro è accessibile dalla classe che lo contiene o dalle classi derivate dichiarate nello stesso assembly. Anche se `protected internal` consente l'accesso da classi derivate o classi nello stesso assembly, `private protected` limita l'accesso ai tipi derivati dichiarati nello stesso assembly.

Per altre informazioni, vedere [Modificatori di accesso](../language-reference/keywords/access-modifiers.md) nelle informazioni di riferimento sul linguaggio.
