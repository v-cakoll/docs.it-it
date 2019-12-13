---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568211"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>.NET Core 3,0 segue le procedure consigliate Unicode per la sostituzione di sequenze di byte UTF-8 in formato non corretto

Quando la classe <xref:System.Text.UTF8Encoding> rileva una sequenza di byte UTF-8 in formato non corretto durante un'operazione di transcodifica da byte a carattere, la sequenza verrà sostituita con il carattere di sostituzione "" (U + FFFD) nella stringa di output. .NET Core 3,0 differisce dalle versioni precedenti di .NET Core e dal .NET Framework seguendo la procedura consigliata Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.

Questa operazione fa parte di un impegno maggiore per migliorare la gestione UTF-8 in .NET, inclusi i nuovi <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> e i tipi di <xref:System.Text.Rune?displayProperty=nameWithType>. Al tipo <xref:System.Text.UTF8Encoding> è stato fornito un meccanismo di gestione degli errori migliorato in modo da produrre output coerente con i nuovi tipi introdotti.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Core 3,0, quando si transcodificano i byte in caratteri, la classe <xref:System.Text.UTF8Encoding> esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode. Il meccanismo di sostituzione usato viene descritto dallo [standard Unicode, versione 12,0, sec. 3,9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione intitolata _U + FFFD Substitution of Maximum Subparts_.

Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto. Inoltre, se l'istanza di <xref:System.Text.UTF8Encoding> è stata costruita con `throwOnInvalidBytes: true` (vedere la [documentazione del costruttore UTF8Encoding] (<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, l'istanza di `UTF8Encoding` continuerà a generare un input non valido anziché eseguire la sostituzione di U + FFFD.

Nell'esempio seguente viene illustrato l'effetto di questa modifica con un input di 3 byte non valido:

|Input a 3 byte in formato non valido|Output prima di .NET Core 3,0|Output a partire da .NET Core 3,0|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]` (output a 2 caratteri)| `[ FFFD FFFD FFFD ]` (output di 3 caratteri)|

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
