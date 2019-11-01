---
ms.openlocfilehash: d888aba597cb6981828ca67fba04912cbcf7935f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198453"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. ApplicationServices non disponibile

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="change-description"></a>Descrizione della modifica

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> sono disponibili in alcune versioni di .NET Core 3,0 Preview. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso di tipi di <xref:Microsoft.VisualBasic.ApplicationServices> e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET. Ad esempio, alcuni <xref:System.Environment?displayProperty=nameWithType> e <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> membri forniscono funzionalità equivalenti alle proprietà della classe <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType>.

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-- >

