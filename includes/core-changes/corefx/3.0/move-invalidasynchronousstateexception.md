---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721581"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>InvalidAsynchronousStateException spostato in un altro assembly

La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.InvalidAsynchronousStateException> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .

A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica riguarda solo le applicazioni che usano la reflection per caricare l'oggetto chiamando <xref:System.ComponentModel.InvalidAsynchronousStateException> un metodo come <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico. In tal caso, aggiornare l'assembly a cui viene fatto riferimento nella chiamata al metodo per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

Nessuno.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
