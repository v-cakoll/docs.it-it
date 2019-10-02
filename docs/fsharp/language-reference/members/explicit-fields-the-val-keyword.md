---
title: 'Campi espliciti: Parola chiave Val'
description: Informazioni sulla parola F# chiave ' Val ', che viene usata per dichiarare un percorso in cui archiviare un valore in un tipo di classe o di struttura senza inizializzare il tipo.
ms.date: 05/16/2016
ms.openlocfilehash: 2703d9a2734cfda1614a401ec24c6630ec31b2f1
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736829"
---
# <a name="explicit-fields-the-val-keyword"></a>Campi espliciti: Parola chiave Val

La parola chiave `val` viene usata per dichiarare un percorso per archiviare un valore in un tipo di classe o struttura senza inizializzarlo. Le posizioni di archiviazione dichiarate in questo modo sono denominate *campi espliciti*. Un altro uso della parola chiave `val` è in combinazione con la parola chiave `member` per dichiarare una proprietà implementata automaticamente. Per ulteriori informazioni sulle proprietà implementate automaticamente, vedere [Proprietà](properties.md).

## <a name="syntax"></a>Sintassi

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Note

La modalità standard per definire i campi in un tipo di classe o struttura consiste nell'usare un'associazione `let`. Tuttavia, le associazioni `let` devono essere inizializzate come parte del costruttore della classe, ma non è sempre possibile, necessario o appropriato. È possibile usare la parola chiave `val` quando si desidera un campo non inizializzato.

I campi espliciti possono essere statici o non statici. Il *modificatore di accesso* può `public`essere `private`, o `internal`. Per impostazione predefinita, i campi espliciti sono pubblici. Questo comportamento è diverso dalle associazioni `let` nelle classi, che invece sono sempre private.

L'attributo [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) è obbligatorio nei campi espliciti nei tipi di classe con un costruttore primario. Questo attributo specifica che il campo viene inizializzato su zero. Il tipo del campo deve supportare l'inizializzazione su zero. Un tipo supporta l'inizializzazione su zero se corrisponde a uno dei seguenti tipi:

- Un tipo primitivo con valore pari a zero.
- Un tipo che supporta un valore null come valore normale, come valore anomalo o come rappresentazione di un valore. Questo include classi, tuple, record, funzioni, interfacce, tipi di riferimento .NET, il tipo `unit` e i tipi di unioni discriminati.
- Un tipo di valore .NET.
- Una struttura in cui tutti i campi supportano un valore predefinito pari a zero.

Ad esempio, un campo non modificabile chiamato `someField` è un campo di supporto nella rappresentazione compilata .NET con il nome `someField@` e si accede al valore archiviato usando una proprietà denominata `someField`.

Per un campo modificabile, la rappresentazione compilata .NET è un campo .NET.

> [!WARNING]
> Lo spazio dei `System.ComponentModel` nomi .NET Framework contiene un attributo con lo stesso nome. Per altre informazioni sull'attributo, vedere <xref:System.ComponentModel.DefaultValueAttribute>.

Nel codice seguente viene illustrato l'uso di campi espliciti e, per il confronto, un'associazione `let` in una classe che dispone di un costruttore primario. Si noti che il campo associato `let``myInt1` è privato. Quando si fa riferimento al campo associato `let``myInt1` da un metodo membro, l'autoidentificatore `this` non è necessario. Ma quando si fa riferimento ai campi espliciti `myInt2` e `myString`, l'autoidentificatore è obbligatorio.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

L'output è indicato di seguito:

```console
11 12 abc
30 def
```

Nel codice seguente viene illustrato come usare i campi espliciti in una classe che non dispone di un costruttore principale. In questo caso, l'attributo `DefaultValue` non è obbligatorio, ma tutti i campi devono essere inizializzati nei costruttori definiti per il tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

L'output è `35 22`.

Nel codice seguente viene illustrato come usare i campi espliciti in una struttura. Poiché una struttura è un tipo valore, dispone automaticamente di un costruttore senza parametri che imposta i valori dei campi su zero. Pertanto l'attributo `DefaultValue` non è obbligatorio.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

L'output è `11 xyz`.

**Prestare attenzione**se si intende inizializzare la struttura con `mutable` i campi senza `mutable` parola chiave, le assegnazioni funzioneranno su una copia della struttura che verrà eliminata subito dopo l'assegnazione. Pertanto la struttura non verrà modificata.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6704.fs)]

I campi espliciti non sono destinati all'uso di routine. In generale, quando possibile è consigliabile usare un'associazione `let` in una classe anziché un campo esplicito. I campi espliciti sono utili in alcuni scenari di interoperabilità, ad esempio quando è necessario definire una struttura che verrà usata in una chiamata platform invoke per un'API nativa o in scenari di interoperabilità COM. Per ulteriori informazioni, vedere [External Functions](../functions/external-functions.md). Un'altra situazione in cui un campo esplicito potrebbe essere necessario è quando si lavora con un generatore di codice F# che genera classi senza un costruttore primario. I campi espliciti sono utili anche per le variabili di thread statiche o per costrutti simili. Per altre informazioni, vedere `System.ThreadStaticAttribute`.

Quando le parole chiave `member val` vengono visualizzate insieme in una definizione di tipo è una definizione di una proprietà implementata automaticamente. Per ulteriori informazioni, vedi [Proprietà](properties.md).

## <a name="see-also"></a>Vedere anche

- [Proprietà](properties.md)
- [Membri](index.md)
- [Associazioni `let` nelle classi](let-bindings-in-classes.md)
