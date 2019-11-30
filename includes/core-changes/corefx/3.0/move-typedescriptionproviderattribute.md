---
ms.openlocfilehash: 4d479636f41095610eaf39f92ad0dad4863ab8b5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568128"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>TypeDescriptionProviderAttribute spostato in un altro assembly

La classe <xref:System.ComponentModel.TypeDescriptionProviderAttribute> è stata spostata.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, la classe <xref:System.ComponentModel.TypeDescriptionProviderAttribute> si trova nell'assembly *System. ComponentModel. TypeConverter* .

A partire da .NET Core 3,0, si trova nell'assembly *System. ObjectModel* .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica riguarda solo le applicazioni che usano la reflection per caricare il tipo di <xref:System.ComponentModel.TypeDescriptionProviderAttribute> chiamando un metodo come <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico. In tal caso, l'assembly a cui viene fatto riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!--

### Affected APIs

- Not detectable via API analysis

-->
