---
ms.openlocfilehash: 0795ee244bf3d1261bbe61dc0c67c3936f427f04
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216387"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>.NET Core 3,0 segue le procedure consigliate Unicode per la sostituzione di sequenze di byte UTF-8 in formato non corretto

Quando la <xref:System.Text.UTF8Encoding> classe rileva una sequenza di byte UTF-8 in formato non corretto durante un'operazione di transcodifica da byte a carattere, la sequenza verrà sostituita con il carattere di sostituzione '' (U + FFFD) nella stringa di output. .NET Core 3,0 differisce dalle versioni precedenti di .NET Core e dal .NET Framework seguendo la procedura consigliata Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.

Questa operazione fa parte di un impegno maggiore per migliorare la gestione UTF-8 in .NET, inclusi i <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> nuovi <xref:System.Text.Rune?displayProperty=nameWithType> tipi e. Al <xref:System.Text.UTF8Encoding> tipo sono stati assegnati meccanismi di gestione degli errori migliorati in modo da produrre output coerente con i nuovi tipi introdotti.

#### <a name="details"></a>Dettagli

A partire da .NET Core 3,0, quando si transcodificano i byte <xref:System.Text.UTF8Encoding> in caratteri, la classe esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode. Il meccanismo di sostituzione usato viene descritto dallo [standard Unicode, versione 12,0, sec. 3,9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione intitolata _U + FFFD Substitution of Maximum Subparts_.

Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto. Inoltre, se l' <xref:System.Text.UTF8Encoding> istanza è stata costruita con `throwOnInvalidBytes: true` (vedere la [documentazione del costruttore UTF8Encoding]<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>(, `UTF8Encoding` l'istanza continuerà a generare un input non valido anziché eseguire U + FFFD sostituzione.

Nell'esempio seguente viene illustrato l'effetto di questa modifica con un input di 3 byte non valido:

|Input a 3 byte in formato non valido|Output prima di .NET Core 3,0|Output a partire da .NET Core 3,0|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]`(output a 2 caratteri)| `[ FFFD FFFD FFFD ]`(output di 3 caratteri)|

Questo output di 3 caratteri è l'output preferito, in base alla _tabella 3-9_ del file PDF standard Unicode collegato in precedenza.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione da parte dello sviluppatore.

#### <a name="category"></a>Category

CoreFx

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
