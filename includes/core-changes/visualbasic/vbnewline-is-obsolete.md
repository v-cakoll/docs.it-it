---
ms.openlocfilehash: 5ef785f476b795a9c53e511d51b2683b99e6da05
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182063"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Constants. vbNewLine è obsoleto

La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) a partire da .NET Core 3,0 Preview 8.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="details"></a>Dettagli

A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> alla costante. L'uso della costante genera un avviso del compilatore. Nelle versioni precedenti di .NET Core e .NET Framework, non è stato contrassegnato come obsoleto.

Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma. La `vbNewLine` costante è equivalente a `\r\n`, la sequenza di caratteri di nuova riga in Windows. Nei sistemi basati su UNIX, il carattere di nuova `\n`riga è.
 
#### <a name="recommended-action"></a>Azione consigliata

Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per `vbNewLine` include la raccomandazione seguente:

> Per un ritorno a capo e un avanzamento riga, usare [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). Per la nuova riga della piattaforma corrente, <xref:System.Environment.NewLine?displayProperty=nameWithType>usare.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

