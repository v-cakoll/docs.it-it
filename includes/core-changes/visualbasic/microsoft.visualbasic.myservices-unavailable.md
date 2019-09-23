---
ms.openlocfilehash: ba543414d4f84362c9b9b876395815e837efbd3f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181774"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. MyServices non disponibili

I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="details"></a>Dettagli

I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.
 
#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso dei tipi **Microsoft. VisualBasic. MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti. Di seguito è riportato un mapping dei tipi **Microsoft. VisualBasic. MyServices** ai tipi di libreria di classi .NET equivalenti:

|Tipo Microsoft. VisualBasic. MyServices|Tipo libreria di classi .NET|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType>per applicazioni WPF, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> per applicazioni Windows Forms| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Tipi nello <xref:System.IO> spazio dei nomi|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Tipi correlati al registro di sistema <xref:Microsoft.Win32> nello spazio dei nomi|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

