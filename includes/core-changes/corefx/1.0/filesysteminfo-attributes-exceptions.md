---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021794"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException generata da FileSystemInfo.Attributes

In .NET Core, viene generato un <xref:System.UnauthorizedAccessException> eccezione quando il chiamante tenta di impostare un valore di attributo di file ma non dispone dell'autorizzazione di scrittura.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework, viene generata un'eccezione <xref:System.ArgumentException> quando <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> il chiamante tenta di impostare un valore dell'attributo di file ma non dispone dell'autorizzazione di scrittura. In .NET Core <xref:System.UnauthorizedAccessException> viene invece generata un'eccezione. In .NET Core <xref:System.ArgumentException> viene comunque generato un messaggio se il chiamante tenta di impostare un attributo di file non valido.

#### <a name="version-introduced"></a>Versione introdotta

1.0

#### <a name="recommended-action"></a>Azione consigliata

Modificare `catch` le istruzioni in <xref:System.UnauthorizedAccessException> modo che rilevi <xref:System.ArgumentException>un'istruzione anziché, o in aggiunta a , in base alle esigenze.

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
