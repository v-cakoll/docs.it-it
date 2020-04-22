---
ms.openlocfilehash: 843c78bb4e4f88d9ac58308a91ab8278364c9580
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021629"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>.NET Core 3.0 segue le procedure consigliate di Unicode quando si sostituiscono sequenze di byte UTF-8 in formato non corretto

Quando <xref:System.Text.UTF8Encoding> la classe rileva una sequenza di byte UTF-8 in formato non corretto durante un'operazione di transcodifica byte-carattere, sostituirà tale sequenza con un carattere ' ' (U -FFFD REPLACEMENT CHARACTER) nella stringa di output. .NET Core 3.0 differisce dalle versioni precedenti di .NET Core e .NET Framework seguendo le procedure consigliate Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.

Questo fa parte di uno sforzo più ampio per migliorare <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> la <xref:System.Text.Rune?displayProperty=nameWithType> gestione UTF-8 in tutta .NET, anche dai nuovi e tipi. Al <xref:System.Text.UTF8Encoding> tipo è stato fornito meccanismi di gestione degli errori migliorati in modo che produca output coerente con i tipi appena introdotti.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3.0, durante <xref:System.Text.UTF8Encoding> la transcodifica di byte in caratteri, la classe esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode.Starting with .NET Core 3.0, when transcoding bytes to characters, the class performs character substitution based on Unicode best practices. Il meccanismo di sostituzione utilizzato è descritto da [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione denominato _Sostituzione U-FFFD delle sottoparti maximal_.

Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto. Inoltre, se <xref:System.Text.UTF8Encoding> l'istanza è `throwOnInvalidBytes: true` stata costruita con (vedere<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>la `UTF8Encoding` [documentazione del costruttore UTF8Encoding]( , l'istanza continuerà a generare un input non valido anziché eseguire la sostituzione di U-FFFD.

Di seguito viene illustrato l'impatto di questa modifica con un input a 3 byte non valido:

|Input a 3 byte in formato non corretto|Output prima di .NET Core 3.0|Output che inizia con .NET Core 3.0|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]`(uscita a 2 caratteri)| `[ FFFD FFFD FFFD ]`(uscita a 3 caratteri)|

Questo output di 3 caratteri è l'output preferito, secondo la _tabella 3-9_ del PDF Standard Unicode precedentemente collegato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione da parte dello sviluppatore.

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
