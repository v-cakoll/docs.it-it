---
ms.openlocfilehash: bb163d5a6eb3d926a44a83ea79572c3a497bbe8d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181768"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile

I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="details"></a>Dettagli

I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.
 
#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso dei tipi e <xref:Microsoft.VisualBasic.Devices> dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> , la <xref:System.DateTime?displayProperty=nameWithType> funzionalità equivalente alla classe viene fornita dai tipi e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> classe viene fornita dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

