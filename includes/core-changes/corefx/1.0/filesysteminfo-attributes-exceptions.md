---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449401"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException generata da FileSystemInfo. Attributes

In .NET Core viene generata un'<xref:System.UnauthorizedAccessException> quando il chiamante tenta di impostare un valore di attributo di file ma non dispone dell'autorizzazione di scrittura.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Framework, viene generata un'<xref:System.ArgumentException> quando il chiamante tenta di impostare un valore di attributo di file in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> ma non dispone dell'autorizzazione di scrittura. In .NET Core viene invece generata un'<xref:System.UnauthorizedAccessException>. In .NET Core viene ancora generata un'<xref:System.ArgumentException> se il chiamante tenta di impostare un attributo di file non valido.

#### <a name="version-introduced"></a>Versione introdotta

1.0

#### <a name="recommended-action"></a>Azione consigliata

Modificare le istruzioni `catch` per intercettare un <xref:System.UnauthorizedAccessException> anziché, o in aggiunta, un <xref:System.ArgumentException>, se necessario.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
