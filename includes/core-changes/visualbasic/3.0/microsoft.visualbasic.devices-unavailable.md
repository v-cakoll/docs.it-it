---
ms.openlocfilehash: 4c47b95e98aca727d9f0eda54a167a71fd53afb9
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567432"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="change-description"></a>Descrizione della modifica

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> sono disponibili in alcune versioni di anteprima di .NET Core 3,0,. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso di tipi di <xref:Microsoft.VisualBasic.Devices> e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> viene fornita dai tipi <xref:System.DateTime?displayProperty=nameWithType> e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> viene fornita dai tipi nello spazio dei nomi <xref:System.IO.Ports?displayProperty=nameWithType>.

#### <a name="category"></a>Category

Visual Basic -

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

