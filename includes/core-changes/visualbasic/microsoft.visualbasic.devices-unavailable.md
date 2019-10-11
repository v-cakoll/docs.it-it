---
ms.openlocfilehash: dae4afa92b8833f326b4eacd00b36bb3e1199cc1
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237377"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="change-description"></a>Descrizione della modifica

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> sono disponibili in alcune versioni di anteprima di .NET Core 3,0,. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.
 
#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso di tipi <xref:Microsoft.VisualBasic.Devices> e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> viene fornita dai tipi <xref:System.DateTime?displayProperty=nameWithType> e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> viene fornita dai tipi nello spazio dei nomi <xref:System.IO.Ports?displayProperty=nameWithType>.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

