---
title: Delegati (F#)
description: Informazioni su come usare i delegati in F#.
ms.date: 05/16/2016
ms.openlocfilehash: be58997dffe8fcd949bbc2d47d86ffccc157d43e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45745494"
---
# <a name="delegates"></a>Delegati

Un delegato rappresenta una chiamata di funzione come oggetto. In F#, è in genere consigliabile usare valori di funzione per rappresentare funzioni come valori di prima classe. Tuttavia, i delegati vengono usati in .NET Framework e pertanto sono necessari quando si interagisce con le API che prevedono li. È possibile usarle anche quando creazione di librerie progettate per utilizzare da altri linguaggi .NET Framework.

## <a name="syntax"></a>Sintassi

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Note

Nella sintassi precedente `type1` rappresenta il tipo di argomento o i tipi e `type2` rappresenta il tipo restituito. I tipi di argomento che sono rappresentati da `type1` automaticamente vengono sottoposti a currying. Ne consegue che per questo tipo è usare un formato di tupla se gli argomenti della funzione di destinazione vengono sottoposti a currying e una tupla tra parentesi per gli argomenti che è già in formato tupla. Il currying automatica rimuove un set di parentesi, lasciando un argomento con tuple che corrisponde al metodo di destinazione. Vedere l'esempio di codice per la sintassi da utilizzare in ogni caso.

I delegati possono essere collegati a, valori di funzione F# e statici o metodi di istanza. I valori di funzione F# possono essere passati direttamente come argomenti al delegato costruttori. Per un metodo statico, il delegato viene costruito usando il nome della classe e il metodo. Per un metodo di istanza, specificare l'istanza dell'oggetto e un metodo in un solo argomento. In entrambi i casi, operatore di accesso ai membri (`.`) viene usato.

Il `Invoke` metodo sul tipo di delegato chiama la funzione incapsulata. Inoltre, i delegati renserlo passabile come valori di funzioni per fare riferimento al nome di metodo Invoke senza le parentesi.

Il codice seguente illustra la sintassi per la creazione di delegati che rappresentano i vari metodi in una classe. A seconda se il metodo è un metodo statico o un metodo di istanza e se questo dispone di argomenti nel modulo sottoposti a currying o il formato di tupla, la sintassi di dichiarazione e l'assegnazione del delegato è leggermente diversa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Il codice seguente illustra alcuni modi diversi che è possibile usare i delegati.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

L'output dell'esempio di codice precedente è come indicato di seguito.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Parametri e argomenti](parameters-and-arguments.md)
- [Eventi](members/events.md)
