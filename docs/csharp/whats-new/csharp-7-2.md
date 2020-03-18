---
title: Novità di C# 7.2
description: Panoramica delle nuove funzionalità in C# 7.2.
ms.date: 08/16/2017
ms.openlocfilehash: 7febefb81bbea6f24690adb05488ad6a18bbf552
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75694595"
---
# <a name="whats-new-in-c-72"></a>Novità di C# 7.2

C# 7.2 è un'altra Point Release che aggiunge numerose funzionalità utili.
Il tema centrale di questa versione è l'uso più efficiente dei tipi valore, evitando inutili copie o allocazioni.

Le funzionalità rimanenti sono piccole e utili.

C# 7.2 usa l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md) per selezionare la versione del linguaggio del compilatore.

Le nuove funzionalità relative al linguaggio in questa versione sono:

- [Tecniche per la scrittura di codice efficiente e sicuro](#safe-efficient-code-enhancements)
  - Una combinazione di miglioramenti della sintassi che consentono l'utilizzo dei tipi valore tramite la semantica di riferimento.
- [Argomenti denominati non finali](#non-trailing-named-arguments)
  - Gli argomenti denominati possono essere seguiti da argomenti posizionali.
- [Caratteri di sottolineatura iniziali nei valori letterali numerici](#leading-underscores-in-numeric-literals)
  - I valori letterali numerici possono ora includere caratteri di sottolineatura iniziali prima di qualsiasi cifra stampata.
- [`private protected`modificatore di accesso](#private-protected-access-modifier)
  - Il modificatore di accesso `private protected` consente l'accesso per le classi derivate nello stesso assembly.
- [Espressioni `ref` condizionali](#conditional-ref-expressions)
  - Il risultato di un'espressione condizionale (`?:`) può ora essere un riferimento.

La parte restante di questo articolo illustra una panoramica di ogni funzionalità. Per ogni funzionalità verranno illustrati i concetti di base e si apprenderà la sintassi. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="safe-efficient-code-enhancements"></a>Miglioramenti per un codice efficiente e sicuro

Le funzionalità del linguaggio introdotte nella versione 7.2 consentono di lavorare con i tipi valore usando allo stesso tempo la semantica di riferimento. Queste funzionalità sono state progettate per migliorare le prestazioni riducendo al minimo la copia dei tipi valore senza dover sostenere le allocazioni di memoria associate all'uso dei tipi riferimento. Le funzionalità includono:

- Il modificatore `in` per i parametri, per specificare che un argomento viene passato per riferimento, ma non modificato dal metodo chiamato. L'aggiunta del modificatore `in` a un argomento è una [modifica compatibile a livello di codice sorgente](version-update-considerations.md#source-compatible-changes).
- Il modificatore `ref readonly` per i valori restituiti dai metodi, per indicare che un metodo restituisce il valore per riferimento, ma non consente scritture su tale oggetto. L'aggiunta del modificatore `ref readonly` è una [modifica compatibile a livello di codice sorgente](version-update-considerations.md#source-compatible-changes), se il valore restituito viene assegnato a un valore. L'aggiunta del modificatore `readonly` a un'istruzione return `ref` esistente è una [modifica incompatibile](version-update-considerations.md#incompatible-changes). Richiede ai chiamanti di aggiornare la dichiarazione delle variabili locali `ref` per includere il modificatore `readonly`.
- La dichiarazione `readonly struct` per indicare che uno struct non è modificabile e deve essere passato come parametro `in` ai relativi metodi membro. L'aggiunta del modificatore `readonly` a una dichiarazione di struct esistente è una [modifica compatibile a livello binario](version-update-considerations.md#binary-compatible-changes).
- La dichiarazione `ref struct` per indicare che un tipo di struct accede direttamente alla memoria gestita e deve sempre essere allocato nello stack. L'aggiunta del modificatore `ref` a una dichiarazione `struct` esistente è una [modifica incompatibile](version-update-considerations.md#incompatible-changes). `ref struct` non può essere un membro di una classe o usato in altre posizioni in cui potrebbe allocato nell'heap.

È possibile leggere altre informazioni su tutte queste modifiche in [Scrivere codice efficiente e sicuro](../write-safe-efficient-code.md).

## <a name="non-trailing-named-arguments"></a>Argomenti denominati non finali

Per le chiamate di metodi è ora possibile usare argomenti denominati che precedono gli argomenti posizionali quando questi argomenti denominati sono nelle posizioni corrette. Per altre informazioni, vedere [Argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Caratteri di sottolineatura iniziali nei valori letterali numerici

L'implementazione del supporto per i separatori di cifre in C# 7.0 non consentiva l'uso di `_` come primo carattere del valore letterale. I valori letterali numerici esadecimali e binari possono ora iniziare con `_`.

Ad esempio:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>Modificatore di accesso *private protected*

Il nuovo modificatore di accesso composto `private protected` indica che un membro è accessibile dalla classe che lo contiene o dalle classi derivate dichiarate nello stesso assembly. Anche se `protected internal` consente l'accesso da classi derivate o classi nello stesso assembly, `private protected` limita l'accesso ai tipi derivati dichiarati nello stesso assembly.

Per altre informazioni, vedere [Modificatori di accesso](../language-reference/keywords/access-modifiers.md) nelle informazioni di riferimento sul linguaggio.

## <a name="conditional-ref-expressions"></a>Espressioni condizionali `ref`

Infine, l'espressione condizionale può produrre un risultato ref invece di un risultato valore. Ad esempio, per recuperare un riferimento al primo elemento in una di due matrici, scrivere il codice seguente:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

La variabile `r` è un riferimento al primo valore in `arr` o `otherArr`.

Per altre informazioni, vedere [Operatore ?:](../language-reference/operators/conditional-operator.md) nelle informazioni di riferimento sul linguaggio.
