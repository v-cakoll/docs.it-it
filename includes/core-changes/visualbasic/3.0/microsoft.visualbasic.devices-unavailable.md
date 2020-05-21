---
ms.openlocfilehash: a35de09b9a7bb9686433205359c3cc55954c29c3
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721285"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile

I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="change-description"></a>Descrizione modifica:

I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso dei <xref:Microsoft.VisualBasic.Devices> tipi e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> classe viene fornita dai <xref:System.DateTime?displayProperty=nameWithType> tipi e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> classe viene fornita dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
