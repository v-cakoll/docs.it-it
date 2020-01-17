---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116342"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft. VisualBasic. MyServices non disponibili

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3,0 Preview 8

#### <a name="change-description"></a>Descrizione delle modifiche

I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> sono disponibili in alcune versioni di .NET Core 3,0 Preview. Non sono più disponibili a partire da .NET Core 3,0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'uso dei tipi **Microsoft. VisualBasic. MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti. Di seguito è riportato un mapping dei tipi **Microsoft. VisualBasic. MyServices** ai tipi di libreria di classi .NET equivalenti:

|Tipo Microsoft. VisualBasic. MyServices|Tipo libreria di classi .NET|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType> per applicazioni WPF <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> per applicazioni Windows Forms|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Tipi nello spazio dei nomi <xref:System.IO>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Tipi correlati al registro di sistema nello spazio dei nomi <xref:Microsoft.Win32>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Categoria

Visual Basic -

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
