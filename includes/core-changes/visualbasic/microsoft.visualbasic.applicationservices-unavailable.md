---
ms.openlocfilehash: c3211752282b231e818d9af25322efbb6c93cf78
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181840"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. ApplicationServices non disponibile

I tipi nello <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="details"></a>Dettagli

I tipi nello <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di .NET Core 3,0 Preview. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.
 
#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso dei tipi e <xref:Microsoft.VisualBasic.ApplicationServices> dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, alcuni <xref:System.Environment?displayProperty=nameWithType> membri <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> e forniscono funzionalità equivalenti <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> alle proprietà della classe.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-- >

