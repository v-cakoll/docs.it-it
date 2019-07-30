---
title: Delegati
description: Informazioni su come usare i delegati in F#.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630365"
---
# <a name="delegates"></a>Delegati

Un delegato rappresenta una chiamata di funzione come un oggetto. In F#, in genere è necessario utilizzare i valori di funzione per rappresentare le funzioni come valori di prima classe; Tuttavia, i delegati vengono usati nell'.NET Framework e pertanto sono necessari quando si interagisce con le API che li prevedono. Possono anche essere usati durante la creazione di librerie progettate per l'uso da altri linguaggi .NET Framework.

## <a name="syntax"></a>Sintassi

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Note

Nella sintassi precedente, `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito. I tipi di argomento rappresentati da `type1` vengono sottoposti a currying automatico. Questo suggerisce che per questo tipo si usa un form di tupla se gli argomenti della funzione di destinazione sono sottoposti a currying e una tupla tra parentesi per gli argomenti già presenti nel form della tupla. Il currying automatico rimuove un set di parentesi, lasciando un argomento di tupla corrispondente al metodo di destinazione. Fare riferimento all'esempio di codice per la sintassi da usare in ogni caso.

I delegati possono F# essere associati a valori di funzione e metodi statici o di istanza. F#i valori della funzione possono essere passati direttamente come argomenti ai costruttori delegati. Per un metodo statico, il delegato viene costruito usando il nome della classe e il metodo. Per un metodo di istanza, è necessario specificare l'istanza e il metodo dell'oggetto in un argomento. In entrambi i casi, viene usato l'operatore`.`di accesso ai membri ().

Il `Invoke` metodo nel tipo delegato chiama la funzione incapsulata. Inoltre, i delegati possono essere passati come valori di funzione facendo riferimento al nome del metodo Invoke senza le parentesi.

Nel codice seguente viene illustrata la sintassi per la creazione di delegati che rappresentano i vari metodi di una classe. A seconda se il metodo è un metodo statico o un metodo di istanza e se dispone di argomenti nel form della tupla o nel form sottoposto a currying, la sintassi per la dichiarazione e l'assegnazione del delegato è leggermente diversa.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Il codice seguente illustra alcuni dei diversi modi in cui è possibile lavorare con i delegati.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

L'output dell'esempio di codice precedente è il seguente.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Parametri e argomenti](parameters-and-arguments.md)
- [Eventi](./members/events.md)
