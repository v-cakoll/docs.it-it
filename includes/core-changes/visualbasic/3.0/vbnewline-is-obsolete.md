---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116320"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Constants. vbNewLine è obsoleto

La costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> è contrassegnata come [\[obsoleta\]](xref:System.ObsoleteAttribute) a partire da .net core 3,0 Preview 8.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="change-description"></a>Descrizione delle modifiche

A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato alla costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>. L'uso della costante genera un avviso del compilatore. In .NET Framework e nelle versioni precedenti di .NET Core, non è stato contrassegnato come obsoleto.

Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma. La costante <xref:Microsoft.VisualBasic.Constants.vbNewLine> è equivalente a `\r\n`, la sequenza di caratteri di nuova riga in Windows. Nei sistemi basati su UNIX, il carattere di nuova riga viene `\n`.

#### <a name="recommended-action"></a>Azione consigliata

Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per <xref:Microsoft.VisualBasic.Constants.vbNewLine> include la raccomandazione seguente:

Per un ritorno a capo e un avanzamento riga, utilizzare <xref:Microsoft.VisualBasic.Constants.vbCrLf>. Per la nuova riga della piattaforma corrente, usare <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Categoria

Visual Basic -

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
