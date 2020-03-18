---
ms.openlocfilehash: 19359422f79f8240676b0057c7391f6b06f961ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147549"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException spostato in un altro assembly

La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e <xref:System.ComponentModel.InvalidAsynchronousStateException> versioni precedenti, la classe si trova nell'assembly *System.ComponentModel.TypeConverter.*

A partire da .NET Core 3.0, si trova nell'assembly *System.ComponentModel.Primitives.*

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica ha effetto solo sulle <xref:System.ComponentModel.InvalidAsynchronousStateException> applicazioni che utilizzano la reflection per caricare l'oggetto chiamando un metodo, ad <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> esempio o un overload che <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> presuppone che il tipo si trova in un determinato assembly. In questo caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

No.

<!--

### Affected APIs

- Not detectable via API analysis

-->
