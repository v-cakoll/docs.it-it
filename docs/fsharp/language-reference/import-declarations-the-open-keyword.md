---
title: 'Dichiarazioni di importazione: parola chiave open (F#)'
description: 'Informazioni sulle dichiarazioni di importazione di F # e come vengono specificati un modulo o dello spazio dei nomi cui elementi è possibile fare riferimento senza usare un nome completo.'
ms.date: 05/16/2016
ms.openlocfilehash: 8cae4b4f5418689bfb0933b7db4ec23a313d5ed8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668730"
---
# <a name="import-declarations-the-open-keyword"></a>Dichiarazioni di importazione: Il `open` (parola chiave)

> [!NOTE]
I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Un' *dichiarazione di importazione* specifica un modulo o i cui elementi è possibile fare riferimento senza usare un nome completo dello spazio dei nomi.

## <a name="syntax"></a>Sintassi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Note

Riferimento al codice utilizzando il percorso completo dello spazio dei nomi o modulo ogni volta possibile creare codice difficile da leggere, scrivere e mantenere. In alternativa, è possibile usare il `open` parola chiave per utilizzati spesso moduli e spazi dei nomi in modo che quando si fa riferimento a un membro di tale modulo o dello spazio dei nomi, è possibile usare la versione abbreviata del nome anziché il nome completo. Questa parola chiave è simile al `using` parola chiave nel linguaggio c# `using namespace` in Visual C++ e `Imports` in Visual Basic.

Il modulo o dello spazio dei nomi fornito deve essere nello stesso progetto o in un progetto di riferimento o un assembly. In caso contrario, è possibile aggiungere un riferimento al progetto o usare il `-reference` comandi`-`opzione della riga (o la relativa abbreviazione `-r`). Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

La dichiarazione di importazione sono disponibili i nomi nel codice che segue la dichiarazione, fino alla fine dell'inclusione dello spazio dei nomi, modulo o file.

Quando si usano più dichiarazioni di importazione, verranno visualizzate in righe separate.

Il codice seguente viene illustrato come utilizzare il `open` (parola chiave) per semplificare il codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Il compilatore F # non genera un errore o un avviso quando le ambiguità si verificano quando si verifica lo stesso nome in più di un modulo aperto o spazio dei nomi. Quando si verificano ambiguità, F # accorda priorità a più file aperti di recente modulo o dello spazio dei nomi. Ad esempio, nel codice seguente, `empty` significa `Seq.empty`, anche se `empty` si trova in entrambi i `List` e `Seq` moduli.

```fsharp
open List
open Seq
printfn "%A" empty
```

Pertanto, prestare attenzione quando si apre, ad esempio i moduli o spazi dei nomi `List` o `Seq` che contengono membri che hanno nomi identici; in alternativa, è consigliabile usare i nomi completi. È consigliabile evitare qualsiasi situazione in cui il codice è dipende dall'ordine delle dichiarazioni di importazione.

## <a name="namespaces-that-are-open-by-default"></a>Spazi dei nomi che sono aperte per impostazione predefinita

Alcuni spazi dei nomi vengono utilizzati con una frequenza nel codice F # che sono aperti in modo implicito senza la necessità di una dichiarazione di importazione esplicita. La tabella seguente mostra gli spazi dei nomi che sono aperte per impostazione predefinita.

|Spazio dei nomi|Descrizione|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene le definizioni dei tipo F # di base per i tipi predefiniti, ad esempio `int` e `float`.|
|`Microsoft.FSharp.Core.Operators`|Contiene operazioni aritmetiche di base, ad esempio `+` e `*`.|
|`Microsoft.FSharp.Collections`|Contiene le classi di raccolte non modificabili, ad esempio `List` e `Array`.|
|`Microsoft.FSharp.Control`|Contiene tipi per i costrutti di controllo, ad esempio la valutazione lazy e flussi di lavoro asincroni.|
|`Microsoft.FSharp.Text`|Contiene funzioni per i/o formattati, ad esempio il `printf` (funzione).|

## <a name="autoopen-attribute"></a>AutoOpen (attributo)

È possibile applicare il `AutoOpen` attributo a un assembly, se si vuole aprire automaticamente un modulo o dello spazio dei nomi quando viene fatto riferimento all'assembly. È inoltre possibile applicare il `AutoOpen` attributo a un modulo a modulo si apre automaticamente quando viene aperto il modulo padre o dello spazio dei nomi. Per altre informazioni, vedere [classe Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess (attributo)

Alcuni moduli, record o i tipi di unione possono specificare il `RequireQualifiedAccess` attributo. Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto che è includere una dichiarazione di importazione. Se si usa questo attributo in modo strategico su tipi che definiscono in genere utilizzati nomi, consente di evitare conflitti di nome e codice più resiliente a modifiche nelle librerie. Per altre informazioni, vedere [classe Core. RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vedere anche

- [C# riferimenti al linguaggio](index.md)
- [Spazi dei nomi](namespaces.md)
- [Moduli](modules.md)
