---
ms.openlocfilehash: 7f528510e4158dad71280a7b1f269a231b8c60f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116361"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft.VisualBasic.Devices non disponibiliTypes in Microsoft.VisualBasic.Devices namespace not available

I tipi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> nello spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0 Anteprima 8

#### <a name="change-description"></a>Descrizione modifica:

I tipi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> nello spazio dei nomi erano disponibili in alcune versioni di .NET Core 3.0 Preview. Non sono più disponibili a partire da .NET Core 3.0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende <xref:Microsoft.VisualBasic.Devices> dall'utilizzo dei tipi e dei relativi membri, è possibile utilizzare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, funzionalità <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> equivalenti alla <xref:System.DateTime?displayProperty=nameWithType> classe <xref:System.Environment?displayProperty=nameWithType> viene fornita dai <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> tipi e funzionalità equivalenti alla classe vengono fornite dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi .

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
