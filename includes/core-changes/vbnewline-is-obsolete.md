---
ms.openlocfilehash: 82017569128937d344838df850445cf55aa9ea4c
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70930033"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft. VisualBasic. Constants. vbNewLine è obsoleto

La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) in .NET Framework, ma l'attributo non era presente in precedenza nella libreria .NET Core 3,0.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="details"></a>Dettagli

A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> alla `vbNewLine` costante per conformarsi a nel .NET Framework. L' `vbNewLine` uso della costante genera un avviso del compilatore. 

Nelle versioni precedenti di .NET Core, `vbNewLine` non ha generato un avviso del compilatore.

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

