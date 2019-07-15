---
ms.openlocfilehash: 7f551fbc194d2da2fdae6bcc7025c20b03aadda2
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859315"
---
### <a name="path-colon-checks-are-stricter"></a>I controlli della presenza di due punti nel percorso sono più severi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 sono state apportate varie modifiche per supportare i percorsi in precedenza non supportati (sia per lunghezza che per formato). I controlli della sintassi corretta del separatore appropriato per le unità (due punti) sono ora più corretti. L'effetto collaterale è però il blocco di alcuni percorsi URI in un gruppo selezionato di API Path in cui l'uso era tollerato.|
|Suggerimento|Per il passaggio di un URI alle API interessate, modificare prima di tutto la stringa in modo che sia un percorso valido.<ul><li>Rimuovere manualmente lo schema dagli URL (ad esempio rimuovere <code>file://</code> dagli URL)</li><li>Passare l'URI alla classe <xref:System.Uri> e usare <xref:System.Uri.LocalPath></li></ul>In alternativa, è possibile rifiutare esplicitamente la nuova normalizzazione dei percorsi impostando l'opzione di AppContext <code>Switch.System.IO.UseLegacyPathHandling</code> su true.|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|

