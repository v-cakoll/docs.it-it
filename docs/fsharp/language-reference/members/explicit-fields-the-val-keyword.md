---
title: 'Campi espliciti: parola chiave val (F#)'
description: 'Informazioni su F # ''val'' parola chiave, che viene utilizzata per dichiarare un percorso per archiviare un valore in un tipo classe o struttura senza inizializzare il tipo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3bdbc745-436b-407f-bf54-5d11ca829cd0
ms.openlocfilehash: cee53a48f08aec89b0bdd40189ed331cadee877d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="explicit-fields-the-val-keyword"></a>Campi espliciti: parola chiave val

La parola chiave `val` viene usata per dichiarare un percorso per archiviare un valore in un tipo di classe o struttura senza inizializzarlo. Percorsi di archiviazione dichiarati in questo modo vengono chiamati *campi espliciti*. Un altro uso della parola chiave `val` è in combinazione con la parola chiave `member` per dichiarare una proprietà implementata automaticamente. Per ulteriori informazioni sulle proprietà implementate automaticamente, vedere [proprietà](properties.md).


## <a name="syntax"></a>Sintassi

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a>Note
La modalità standard per definire i campi in un tipo di classe o struttura consiste nell'usare un'associazione `let`. Tuttavia, le associazioni `let` devono essere inizializzate come parte del costruttore della classe, ma non è sempre possibile, necessario o appropriato. È possibile usare la parola chiave `val` quando si desidera un campo non inizializzato.

I campi espliciti possono essere statici o non statici. Il *modificatore di accesso* può essere `public`, `private`, o `internal`. Per impostazione predefinita, i campi espliciti sono pubblici. Questo comportamento è diverso dalle associazioni `let` nelle classi, che invece sono sempre private.

Il [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attributo è obbligatorio nei campi espliciti nei tipi di classe che dispone di un costruttore primario. Questo attributo specifica che il campo viene inizializzato su zero. Il tipo del campo deve supportare l'inizializzazione su zero. Un tipo supporta l'inizializzazione su zero se corrisponde a uno dei seguenti tipi:

- Un tipo primitivo con valore pari a zero.

- Un tipo che supporta un valore null come valore normale, come valore anomalo o come rappresentazione di un valore. Questo include classi, tuple, record, funzioni, interfacce, tipi di riferimento .NET, il tipo `unit` e i tipi di unioni discriminati.

- Un tipo di valore .NET.

- Una struttura in cui tutti i campi supportano un valore predefinito pari a zero.


Ad esempio, un campo non modificabile chiamato `someField` è un campo di supporto nella rappresentazione compilata .NET con il nome `someField@` e si accede al valore archiviato usando una proprietà denominata `someField`.

Per un campo modificabile, la rappresentazione compilata .NET è un campo .NET.


>[!WARNING] 
`Note`Lo spazio dei nomi .NET Framework `System.ComponentModel` contiene un attributo con lo stesso nome. Per altre informazioni sull'attributo, vedere `System.ComponentModel.DefaultValueAttribute`.


Nel codice seguente viene illustrato l'uso di campi espliciti e, per il confronto, un'associazione `let` in una classe che dispone di un costruttore primario. Si noti che il campo associato `let` `myInt1` è privato. Quando si fa riferimento al campo associato `let` `myInt1` da un metodo membro, l'autoidentificatore `this` non è necessario. Ma quando si fa riferimento ai campi espliciti `myInt2` e `myString`, l'autoidentificatore è obbligatorio.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

L'output è indicato di seguito:

```
11 12 abc
30 def
```

Nel codice seguente viene illustrato come usare i campi espliciti in una classe che non dispone di un costruttore principale. In questo caso, l'attributo `DefaultValue` non è obbligatorio, ma tutti i campi devono essere inizializzati nei costruttori definiti per il tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

L'output è `35 22`.

Nel codice seguente viene illustrato come usare i campi espliciti in una struttura. Poiché una struttura è un tipo di valore, dispone automaticamente di un costruttore predefinito che imposta i valori dei campi su zero. Pertanto l'attributo `DefaultValue` non è obbligatorio.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

L'output è `11 xyz`.

I campi espliciti non sono destinati all'uso di routine. In generale, quando possibile è consigliabile usare un'associazione `let` in una classe anziché un campo esplicito. I campi espliciti sono utili in alcuni scenari di interoperabilità, ad esempio quando è necessario definire una struttura che verrà usata in una chiamata platform invoke per un'API nativa o in scenari di interoperabilità COM. Per ulteriori informazioni, vedere [funzioni esterne](../functions/external-functions.md). Un'altra situazione in cui un campo esplicito potrebbe essere necessario è quando si lavora con un generatore di codice F# che genera classi senza un costruttore primario. I campi espliciti sono utili anche per le variabili di thread statiche o per costrutti simili. Per altre informazioni, vedere `System.ThreadStaticAttribute`.

Quando le parole chiave `member val` vengono visualizzate insieme in una definizione di tipo è una definizione di una proprietà implementata automaticamente. Per ulteriori informazioni, vedere [proprietà](properties.md).


## <a name="see-also"></a>Vedere anche
[Proprietà](properties.md)

[Membri](index.md)

[Associazioni `let` nelle classi](let-bindings-in-classes.md)
