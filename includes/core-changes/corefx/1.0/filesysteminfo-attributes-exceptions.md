---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449401"
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

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
