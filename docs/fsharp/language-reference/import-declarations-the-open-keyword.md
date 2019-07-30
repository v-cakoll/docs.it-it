---
title: 'Dichiarazioni di importazione: Parola chiave open'
description: Informazioni sulle F# dichiarazioni di importazione e sul modo in cui specificano un modulo o uno spazio dei nomi i cui elementi possono fare riferimento senza usare un nome completo.
ms.date: 04/04/2019
ms.openlocfilehash: 816bac551692c3397290f64c6267ee22e4ce90fb
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630569"
---
# <a name="import-declarations-the-open-keyword"></a>Dichiarazioni di importazione: Parola chiave `open`

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Una *dichiarazione di importazione* specifica un modulo o uno spazio dei nomi i cui elementi possono fare riferimento senza usare un nome completo.

## <a name="syntax"></a>Sintassi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Note

Il riferimento al codice tramite lo spazio dei nomi completo o il percorso del modulo ogni volta può creare codice difficile da scrivere, leggere e gestire. È invece possibile usare la `open` parola chiave per i moduli e gli spazi dei nomi usati di frequente in modo che, quando si fa riferimento a un membro di tale modulo o spazio dei nomi, sia possibile usare la forma breve del nome anziché il nome completo. Questa parola chiave è simile alla `using` parola chiave C#in `using namespace` , in C++Visual e `Imports` in Visual Basic.

Il modulo o lo spazio dei nomi specificato deve trovarsi nello stesso progetto o in un progetto o in un assembly a cui si fa riferimento. In caso contrario, è possibile aggiungere un riferimento al progetto oppure utilizzare l'opzione della `-reference` riga di comando`-` `-r`(o la relativa abbreviazione). Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

La dichiarazione di importazione rende disponibili i nomi nel codice che segue la dichiarazione, fino alla fine dello spazio dei nomi, modulo o file di inclusione.

Quando si usano più dichiarazioni di importazione, queste devono essere visualizzate in righe separate.

Il codice seguente illustra l'uso della `open` parola chiave per semplificare il codice.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Il F# compilatore non genera un errore o un avviso quando si verificano ambiguità quando lo stesso nome si verifica in più di un modulo o uno spazio dei nomi aperto. Quando si verificano ambiguità, F# fornisce la preferenza al modulo o allo spazio dei nomi aperti più di recente. Ad esempio, nel codice seguente, `empty` significa `Seq.empty`anche se `empty` si trova in entrambi i `List` moduli e `Seq` .

```fsharp
open List
open Seq
printfn "%A" empty
```

Pertanto, prestare attenzione quando si aprono i moduli o gli spazi `List` dei `Seq` nomi, ad esempio o, che contengono membri con nomi identici. è invece consigliabile utilizzare i nomi completi. È consigliabile evitare situazioni in cui il codice dipende dall'ordine delle dichiarazioni di importazione.

## <a name="namespaces-that-are-open-by-default"></a>Spazi dei nomi aperti per impostazione predefinita

Alcuni spazi dei nomi vengono usati di frequente F# nel codice che vengono aperti in modo implicito senza la necessità di una dichiarazione di importazione esplicita. La tabella seguente Mostra gli spazi dei nomi aperti per impostazione predefinita.

|Spazio dei nomi|Descrizione|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene `int` le F# definizioni di tipo di base per i tipi incorporati `float`, ad esempio e.|
|`Microsoft.FSharp.Core.Operators`|Contiene operazioni aritmetiche di `+` base, ad esempio e. `*`|
|`Microsoft.FSharp.Collections`|Contiene classi di `List` raccolte non modificabili, `Array`ad esempio e.|
|`Microsoft.FSharp.Control`|Contiene i tipi per i costrutti di controllo, ad esempio la valutazione lazy e i flussi di lavoro asincroni.|
|`Microsoft.FSharp.Text`|Contiene funzioni per io formattato, ad esempio `printf` la funzione.|

## <a name="autoopen-attribute"></a>Attributo AutoOpen

È possibile applicare l' `AutoOpen` attributo a un assembly se si desidera aprire automaticamente uno spazio dei nomi o un modulo quando si fa riferimento all'assembly. È anche possibile applicare l' `AutoOpen` attributo a un modulo per aprire automaticamente il modulo quando viene aperto il modulo o lo spazio dei nomi padre. Per altre informazioni, vedere [Classe Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>Attributo RequireQualifiedAccess

Alcuni moduli, record o tipi di Unione possono specificare l' `RequireQualifiedAccess` attributo. Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo, indipendentemente dal fatto che si includa una dichiarazione di importazione. Se si utilizza questo attributo in modo strategico sui tipi che definiscono nomi comunemente utilizzati, è possibile evitare conflitti di nomi e quindi rendere il codice più resiliente alle modifiche nelle librerie. Per altre informazioni, vedere [Classe Core. RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Spazi dei nomi](namespaces.md)
- [Moduli](modules.md)
