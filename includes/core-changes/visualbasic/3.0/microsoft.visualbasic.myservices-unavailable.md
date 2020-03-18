---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116342"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Tipi nello spazio dei nomi Microsoft.VisualBasic.MyServices non disponibiliTypes in Microsoft.VisualBasic.MyServices namespace not available

I tipi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> nello spazio dei nomi non sono disponibili.

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0 Anteprima 8

#### <a name="change-description"></a>Descrizione modifica:

I tipi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> nello spazio dei nomi erano disponibili in alcune versioni di .NET Core 3.0 Preview.The types in the namespace were available in some .NET Core 3.0 Preview releases. Non sono più disponibili a partire da .NET Core 3.0 Preview 9.

I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.

#### <a name="recommended-action"></a>Azione consigliata

Se il codice dipende dall'utilizzo dei tipi **Microsoft.VisualBasic.MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti. Di seguito è riportato un mapping dei tipi **Microsoft.VisualBasic.MyServices** ai tipi di libreria di classi .NET equivalenti:

|Microsoft.VisualBasic.MyServices (tipo)|Tipo di libreria di classi .NET|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType>per le <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> applicazioni WPFWPF, per le applicazioni Windows FormFor WPFWPF applications, for Windows Forms applications|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Tipi nello <xref:System.IO> spazio dei nomiTypes in the namespace|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Tipi correlati al <xref:Microsoft.Win32> Registro di sistema nello spazio dei nomiRegistry-related types in the namespace|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Category

Visual Basic

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
