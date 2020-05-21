---
ms.openlocfilehash: 535a73c6b748166a1e4a4661a6bab0671c653278
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721155"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Constants. vbNewLine è obsoleto

La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [ \[ \] obsoleta](xref:System.ObsoleteAttribute) a partire da .NET Core 3,0 Preview 8.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato alla <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante. L'uso della costante genera un avviso del compilatore. In .NET Framework e nelle versioni precedenti di .NET Core, non è stato contrassegnato come obsoleto.

Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma. La <xref:Microsoft.VisualBasic.Constants.vbNewLine> costante è equivalente a `\r\n` , la sequenza di caratteri di nuova riga in Windows. Nei sistemi basati su UNIX, il carattere di nuova riga è `\n` .

#### <a name="recommended-action"></a>Azione consigliata

Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per <xref:Microsoft.VisualBasic.Constants.vbNewLine> include la raccomandazione seguente:

Per un ritorno a capo e un avanzamento riga, usare <xref:Microsoft.VisualBasic.Constants.vbCrLf> . Per la nuova riga della piattaforma corrente, usare <xref:System.Environment.NewLine?displayProperty=nameWithType> .

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
