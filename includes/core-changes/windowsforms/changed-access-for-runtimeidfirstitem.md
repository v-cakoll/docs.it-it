---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002997"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem

A partire da .NET Core 3,0 RC1, l'accessibilità di `AccessibleObject.RuntimeIDFirstItem` è cambiata da `protected` a `internal`.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Core 3,0 Preview 4, il campo `AccessibleObject.RuntimeIDFirstItem` era `protected`. A partire da .NET Core 3,0 RC1, è stato modificato da `protected` a `internal` per allinearsi con l'accessibilità del campo nella .NET Framework.

#### <a name="version-introduced"></a>Versione introdotta

3,0 RC1

#### <a name="recommended-action"></a>Azione consigliata

La modifica può interessare l'utente se è stata sviluppata un'app .NET Core con un tipo che deriva da <xref:System.Windows.Forms.AccessibleObject> e accede al campo `RuntimeIDFirstItem`. In tal caso, è possibile definire una costante locale come indicato di seguito:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- Non rilevabile tramite l'analisi dell'API.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
