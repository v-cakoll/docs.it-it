---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74644047"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Modifica dell'accesso per AccessibleObject.RuntimeIDFirstItem

A partire da .NET Core 3.0 `AccessibleObject.RuntimeIDFirstItem` RC1, l'accessibilità di è stata modificata da `protected` a `internal`.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3.0 Preview 4, il `AccessibleObject.RuntimeIDFirstItem` campo era `protected`. A partire da .NET Core 3.0 `protected` RC1, è stato modificato da per `internal` allinearsi all'accessibilità del campo in .NET Framework.

#### <a name="version-introduced"></a>Versione introdotta

3.0 RC1

#### <a name="recommended-action"></a>Azione consigliata

La modifica può influire sull'utente se è stata sviluppata un'app .NET Core con un tipo che deriva da <xref:System.Windows.Forms.AccessibleObject> e accede al `RuntimeIDFirstItem` campo. In questo caso, è possibile definire una costante locale come segue:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- Non rilevabile tramite l'analisi API.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
