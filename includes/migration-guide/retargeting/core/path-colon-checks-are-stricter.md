---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614481"
---
### <a name="path-colon-checks-are-stricter"></a>I controlli della presenza di due punti nel percorso sono più severi

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2 sono state apportate varie modifiche per supportare i percorsi in precedenza non supportati (sia per lunghezza che per formato). I controlli della sintassi corretta del separatore appropriato per le unità (due punti) sono ora più corretti. L'effetto collaterale è però il blocco di alcuni percorsi URI in un gruppo selezionato di API Path in cui l'uso era tollerato.

#### <a name="suggestion"></a>Suggerimento

Per il passaggio di un URI alle API interessate, modificare prima di tutto la stringa in modo che sia un percorso valido.<ul><li>Rimuovere manualmente lo schema dagli URL (ad esempio rimuovere `file://` dagli URL)

- Passare l'URI alla classe <xref:System.Uri> e usare <xref:System.Uri.LocalPath>

In alternativa, è possibile rifiutare esplicitamente la nuova normalizzazione dei percorsi impostando l'opzione di AppContext `Switch.System.IO.UseLegacyPathHandling` su true.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
