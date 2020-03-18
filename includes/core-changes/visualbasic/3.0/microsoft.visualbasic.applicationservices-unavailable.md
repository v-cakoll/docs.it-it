---
ms.openlocfilehash: d8cc506d60f3c24087ebde8ead345656fea0f484
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116373"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft.VisualBasic.ApplicationServices non disponibiliTypes in Microsoft.VisualBasic.ApplicationServices namespace not available

I tipi <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> nello spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0 Anteprima 8

#### <a name="change-description"></a>Descrizione modifica:

I tipi <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> nello spazio dei nomi erano disponibili in alcune versioni di .NET Core 3.0 Preview.The types in the namespace were available in some .NET Core 3.0 Preview releases. Non sono più disponibili a partire da .NET Core 3.0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende <xref:Microsoft.VisualBasic.ApplicationServices> dall'utilizzo dei tipi e dei relativi membri, è possibile utilizzare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, <xref:System.Environment?displayProperty=nameWithType> <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> alcuni membri e forniscono <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> funzionalità equivalenti alle proprietà della classe.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
