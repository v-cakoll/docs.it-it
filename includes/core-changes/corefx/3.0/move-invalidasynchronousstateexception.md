---
ms.openlocfilehash: d1562cb76f37b6cc2aeb6fe2f7c17c393e169e84
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158476"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException spostato in un altro assembly

La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.InvalidAsynchronousStateException> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .

A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica riguarda solo le applicazioni che usano la reflection per <xref:System.ComponentModel.InvalidAsynchronousStateException> caricare l'oggetto chiamando un metodo <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> come o un overload <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> di che presuppone che il tipo sia in un assembly specifico. In tal caso, aggiornare l'assembly a cui viene fatto riferimento nella chiamata al metodo per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

Nessuno.

<!--

### Affected APIs

- Not detectable via API analysis

-->
