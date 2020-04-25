---
ms.openlocfilehash: becae23cd810623bbb33c693b707c2d4735aeece
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158475"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a>La sostituzione di sequenze di byte UTF-8 in formato non corretto segue le linee guida Unicode

Quando la <xref:System.Text.UTF8Encoding> classe rileva una sequenza di byte UTF-8 non corretta durante un'operazione di transcodifica da byte a carattere, sostituisce quella sequenza con un carattere di sostituzione '' (U + FFFD) nella stringa di output. .NET Core 3,0 differisce dalle versioni precedenti di .NET Core e dal .NET Framework seguendo la procedura consigliata Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.

Questa operazione fa parte di un impegno maggiore per migliorare la gestione UTF-8 in .NET, inclusi i <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> nuovi <xref:System.Text.Rune?displayProperty=nameWithType> tipi e. Al <xref:System.Text.UTF8Encoding> tipo sono stati assegnati meccanismi di gestione degli errori migliorati in modo da produrre output coerente con i nuovi tipi introdotti.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3,0, quando si transcodificano i byte <xref:System.Text.UTF8Encoding> in caratteri, la classe esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode. Il meccanismo di sostituzione usato viene descritto dallo [standard Unicode, versione 12,0, sec. 3,9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione intitolata _U + FFFD Substitution of Maximum Subparts_.

Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto. Inoltre, se l' <xref:System.Text.UTF8Encoding> istanza è stata costruita con `throwOnInvalidBytes: true`, l' `UTF8Encoding` istanza continuerà a generare un input non valido anziché eseguire la sostituzione di U + FFFD. Per ulteriori informazioni sul `UTF8Encoding` costruttore, vedere. <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>

La tabella seguente illustra l'effetto di questa modifica con un input di 3 byte non valido:

| Input a 3 byte in formato non valido | Output prima di .NET Core 3,0          | Output a partire da .NET Core 3,0        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | `[ FFFD FFFD ]`(output a 2 caratteri) | `[ FFFD FFFD FFFD ]`(output di 3 caratteri) |

L'output di 3 caratteri è l'output preferito, in base alla _tabella 3-9_ del file PDF standard Unicode collegato in precedenza.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione da parte dello sviluppatore.

#### <a name="category"></a>Category

Principali librerie .NET

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
