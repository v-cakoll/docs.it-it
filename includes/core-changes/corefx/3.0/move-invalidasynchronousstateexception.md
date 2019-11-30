---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568171"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException spostato in un altro assembly

La classe <xref:System.ComponentModel.InvalidAsynchronousStateException> è stata spostata.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, la classe <xref:System.ComponentModel.InvalidAsynchronousStateException> si trova nell'assembly *System. ComponentModel. TypeConverter* .

A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica riguarda solo le applicazioni che usano la reflection per caricare il <xref:System.ComponentModel.InvalidAsynchronousStateException> chiamando un metodo come <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico. In tal caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- nessuna

<!--

### Affected APIs

- Not detectable via API analysis

-->
