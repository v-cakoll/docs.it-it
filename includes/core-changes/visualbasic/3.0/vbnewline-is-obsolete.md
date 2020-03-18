---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116320"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine è obsoleto

La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [ \[Obsolete\] ](xref:System.ObsoleteAttribute) a partire da .NET Core 3.0 Preview 8.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 8

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3.0 Preview 8, <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> l'attributo [Obsolete](xref:System.ObsoleteAttribute) è stato applicato alla costante. L'utilizzo della costante genera un avviso del compilatore. In .NET Framework e nelle versioni precedenti di .NET Core, non è stato contrassegnato come obsoleto.

Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma. La <xref:Microsoft.VisualBasic.Constants.vbNewLine> costante è `\r\n`equivalente a , la sequenza di caratteri di nuova riga in Windows. Nei sistemi basati su Unix, `\n`il carattere di nuova riga è .

#### <a name="recommended-action"></a>Azione consigliata

Il messaggio di <xref:Microsoft.VisualBasic.Constants.vbNewLine> attributo [Obsolete](xref:System.ObsoleteAttribute) per include la seguente raccomandazione:

Per un ritorno a capo <xref:Microsoft.VisualBasic.Constants.vbCrLf>e l'avanzamento riga, utilizzare . Per la nuova riga della <xref:System.Environment.NewLine?displayProperty=nameWithType>piattaforma corrente, utilizzare .

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
