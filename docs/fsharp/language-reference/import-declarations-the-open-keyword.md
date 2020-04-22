---
title: 'Dichiarazioni di importazione: parola chiave open'
description: Informazioni sulle dichiarazioni di importazione di F e su come specificano un modulo o uno spazio dei nomi a cui è possibile fare riferimento gli elementi senza usare un nome completo.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021538"
---
# <a name="import-declarations-the-open-keyword"></a>Dichiarazioni di importazione: parola chiave `open`

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Una *dichiarazione* di importazione specifica un modulo o uno spazio dei nomi i cui elementi possono fare riferimento senza utilizzare un nome completo.

## <a name="syntax"></a>Sintassi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Osservazioni

Il riferimento al codice tramite lo spazio dei nomi completo o il percorso del modulo ogni volta può creare codice difficile da scrivere, leggere e gestire. In alternativa, è `open` possibile utilizzare la parola chiave per i moduli e gli spazi dei nomi utilizzati di frequente in modo che quando si fa riferimento a un membro di tale modulo o spazio dei nomi, è possibile utilizzare la forma breve del nome anziché il nome completo. Questa parola chiave `using` è simile alla `using namespace` parola chiave in `Imports` C, in Visual C

Il modulo o lo spazio dei nomi fornito deve trovarsi nello stesso progetto o in un progetto o un assembly di riferimento. In caso contrario, è possibile aggiungere un riferimento `-reference` al progetto o utilizzare l'opzione della riga di comando (o la relativa abbreviazione, `-r`). Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

La dichiarazione di importazione rende disponibili i nomi nel codice che segue la dichiarazione, fino alla fine dello spazio dei nomi, del modulo o del file che lo contiene.

Quando si utilizzano più dichiarazioni di importazione, queste devono essere visualizzate su righe separate.

Nel codice seguente viene `open` illustrato l'utilizzo della parola chiave per semplificare il codice.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Quando si verificano ambiguità quando si verifica lo stesso nome in più di un modulo o spazio dei nomi aperto, il compilatore F non genera un errore o un avviso. Quando si verificano ambiguità, F , fornisce la preferenza al modulo o allo spazio dei nomi aperto più di recente. Nel codice seguente, ad `empty` `Seq.empty`esempio, `empty` si intende , `List` `Seq` anche se si trova in entrambi i moduli e .

```fsharp
open List
open Seq
printfn "%A" empty
```

Pertanto, prestare attenzione quando si `List` aprono moduli o spazi dei nomi, ad esempio o `Seq` che contengono membri con nomi identici. invece, prendere in considerazione l'utilizzo dei nomi completi. È consigliabile evitare qualsiasi situazione in cui il codice dipende dall'ordine delle dichiarazioni di importazione.

## <a name="namespaces-that-are-open-by-default"></a>Spazi dei nomi aperti per impostazione predefinitaNamespaces That Are Open by Default

Alcuni spazi dei nomi vengono usati così di frequente nel codice F , che vengono aperti in modo implicito senza la necessità di una dichiarazione di importazione esplicita. Nella tabella seguente vengono illustrati gli spazi dei nomi aperti per impostazione predefinita.

|Spazio dei nomi|Descrizione|
|---------|-----------|
|`Microsoft.FSharp.Core`|Contiene le definizioni di base dei `int` tipi `float`F , per i tipi incorporati, ad esempio e .|
|`Microsoft.FSharp.Core.Operators`|Contiene operazioni aritmetiche `+` `*`di base come e .|
|`Microsoft.FSharp.Collections`|Contiene classi di raccolte non `List` `Array`modificabili, ad esempio e .|
|`Microsoft.FSharp.Control`|Contiene i tipi per i costrutti di controllo, ad esempio la valutazione lazy e i flussi di lavoro asincroni.|
|`Microsoft.FSharp.Text`|Contiene funzioni per l'I/O `printf` formattato, ad esempio la funzione.|

## <a name="autoopen-attribute"></a>Attributo AutoOpen

È possibile `AutoOpen` applicare l'attributo a un assembly se si desidera aprire automaticamente uno spazio dei nomi o un modulo quando si fa riferimento all'assembly. È inoltre possibile `AutoOpen` applicare l'attributo a un modulo per aprire automaticamente tale modulo quando viene aperto il modulo padre o lo spazio dei nomi. Per ulteriori informazioni, vedere [Classe Core.AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>Attributo RequireQualifiedAccess

Alcuni moduli, record o tipi `RequireQualifiedAccess` di unione possono specificare l'attributo. Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto che si includa una dichiarazione di importazione. Se si utilizza questo attributo in modo strategico nei tipi che definiscono i nomi di uso comune, è possibile evitare conflitti di nomi e quindi rendere il codice più resiliente alle modifiche nelle librerie. Per ulteriori informazioni, vedere [Classe Core.RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
- [Spazi dei nomi](namespaces.md)
- [Moduli](modules.md)
