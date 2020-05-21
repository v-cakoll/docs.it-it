---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721604"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem

A partire da .NET Core 3,0 RC1, l'accessibilità di `AccessibleObject.RuntimeIDFirstItem` è cambiata da `protected` a `internal` .

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3,0 Preview 4, il `AccessibleObject.RuntimeIDFirstItem` campo era `protected` . A partire da .NET Core 3,0 RC1, è stato modificato da `protected` a `internal` per allinearsi all'accessibilità del campo nell'.NET Framework.

#### <a name="version-introduced"></a>Versione introdotta

3,0 RC1

#### <a name="recommended-action"></a>Azione consigliata

La modifica può interessare l'utente se è stata sviluppata un'app .NET Core con un tipo che deriva da <xref:System.Windows.Forms.AccessibleObject> e accede al `RuntimeIDFirstItem` campo. In tal caso, è possibile definire una costante locale come indicato di seguito:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- Non rilevabile tramite l'analisi dell'API.

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
