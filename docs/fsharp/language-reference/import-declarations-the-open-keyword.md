---
title: 'Dichiarazioni di importazione: parola chiave open (F#)'
description: "Informazioni sulle dichiarazioni di importazione di F # e come vengono specificati di un modulo o spazio dei nomi i cui elementi è possibile fare riferimento senza utilizzare un nome completo."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a>Dichiarazioni di importazione: Il `open` (parola chiave)

> [!NOTE]
I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Un *una dichiarazione di importazione* Specifica spazio dei nomi i cui elementi è possibile fare riferimento senza utilizzare un nome completo o un modulo.


## <a name="syntax"></a>Sintassi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Note
Riferimento al codice utilizzando il percorso completo di spazio dei nomi o modulo ogni volta possibile creare codice difficile da leggere, scrivere e mantenere. In alternativa, è possibile utilizzare il `open` parola chiave per utilizzati spesso i moduli e gli spazi dei nomi in modo che quando si fa riferimento a un membro di tale modulo o spazio dei nomi, è possibile utilizzare la forma abbreviata del nome anziché il nome completo. Questa parola chiave è simile al `using` (parola chiave) in c#, `using namespace` in Visual C++, e `Imports` in Visual Basic.

Il modulo o spazio dei nomi fornito deve essere nello stesso progetto o in un progetto di riferimento o un assembly. In caso contrario, è possibile aggiungere un riferimento al progetto o utilizzare il `-reference` comando`-`opzione della riga (o la relativa abbreviazione, `-r`). Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

La dichiarazione di importazione rende i nomi disponibili nel codice che segue la dichiarazione, fino alla fine di inclusione dello spazio dei nomi, modulo o file.

Quando si utilizzano più dichiarazioni di importazione, verranno visualizzate su righe separate.

Il codice seguente viene illustrato come utilizzare il `open` (parola chiave) per semplificare il codice.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Il compilatore F # non genera un errore o un avviso in caso di ambiguità quando si verifica lo stesso nome in più di uno spazio dei nomi o modulo aperto. In caso di ambiguità, F # offre preferenza al modulo o spazio dei nomi aperti più di recente. Ad esempio, nel codice seguente, `empty` significa `Seq.empty`, anche se `empty` si trova in entrambi i `List` e `Seq` moduli.

```fsharp
open List
open Seq
printfn "%A" empty
```

Di conseguenza, prestare attenzione quando si aprono moduli o spazi dei nomi, ad esempio `List` o `Seq` contenenti membri con nomi identici; in alternativa, è consigliabile utilizzare nomi completi. È consigliabile evitare qualsiasi situazione in cui il codice dipende dall'ordine delle dichiarazioni di importazione.


## <a name="namespaces-that-are-open-by-default"></a>Spazi dei nomi aperta per impostazione predefinita
Alcuni spazi dei nomi vengono utilizzati frequentemente nel codice F # che sono aperti in modo implicito senza necessità di una dichiarazione di importazione esplicita. La tabella seguente illustra gli spazi dei nomi che sono aperti per impostazione predefinita.

|Spazio dei nomi|Descrizione|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene le definizioni dei tipo F # di base per i tipi predefiniti, ad esempio `int` e `float`.|
|`Microsoft.FSharp.Core.Operators`|Contiene operazioni aritmetiche di base, ad esempio `+` e `*`.|
|`Microsoft.FSharp.Collections`|Contiene le classi di raccolta non modificabile, ad esempio `List` e `Array`.|
|`Microsoft.FSharp.Control`|Contiene tipi per i costrutti di controllo, ad esempio la valutazione lazy e flussi di lavoro asincroni.|
|`Microsoft.FSharp.Text`|Contiene le funzioni per i/o formattato, ad esempio il `printf` (funzione).|

## <a name="autoopen-attribute"></a>AutoOpen (attributo)
È possibile applicare il `AutoOpen` attributo a un assembly, se si desidera aprire automaticamente un modulo o spazio dei nomi quando viene fatto riferimento all'assembly. È inoltre possibile applicare il `AutoOpen` attributo a un modulo per aprire automaticamente tale modulo quando viene aperto il modulo padre o spazio dei nomi. Per ulteriori informazioni, vedere [classe Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess (attributo)
Alcuni moduli, record o i tipi di unione possono specificare il `RequireQualifiedAccess` attributo. Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto se si include una dichiarazione di importazione. Se si usa questo attributo in modo strategico in tipi che definiscono in genere utilizzati nomi, consente di evitare conflitti di nome e codice molto più adattabile a modifiche nelle librerie. Per ulteriori informazioni, vedere [classe Core. RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).


## <a name="see-also"></a>Vedere anche
[C# riferimenti al linguaggio](index.md)

[Spazi dei nomi](namespaces.md)

[Moduli](modules.md)

