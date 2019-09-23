---
ms.openlocfilehash: 4b41e5fcb6da638457ca8029a635f391b6a7b8ec
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182082"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException spostato in un altro assembly

La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.InvalidAsynchronousStateException> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .

A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica riguarda solo le applicazioni che usano la reflection per <xref:System.ComponentModel.InvalidAsynchronousStateException> caricare l'oggetto chiamando un metodo <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> come o un overload <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> di che presuppone che il tipo sia in un assembly specifico. In tal caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->