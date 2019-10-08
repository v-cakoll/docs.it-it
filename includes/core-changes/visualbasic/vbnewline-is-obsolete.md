---
ms.openlocfilehash: f7c13688236f3d66f3225ecf5d93b4c3284e2e71
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002899"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Constants. vbNewLine è obsoleto

La costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) a partire da .net core 3,0 Preview 8.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="details"></a>Dettagli

A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato alla costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>. L'uso della costante genera un avviso del compilatore. Nelle versioni precedenti di .NET Core e .NET Framework, non è stato contrassegnato come obsoleto.

Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma. La costante `vbNewLine` equivale a `\r\n`, la sequenza di caratteri di nuova riga in Windows. Nei sistemi basati su UNIX, il carattere di nuova riga è `\n`.
 
#### <a name="recommended-action"></a>Azione consigliata

Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per `vbNewLine` include la raccomandazione seguente:

> Per un ritorno a capo e un avanzamento riga, usare [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). Per la nuova riga della piattaforma corrente, usare <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

