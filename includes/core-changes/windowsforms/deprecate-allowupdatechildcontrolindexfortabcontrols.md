---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181804"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. AllowUpdateChildControlIndexForTabControls non supportata

L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità è supportata in Windows Forms in .NET Framework 4,6 e versioni successive, ma non è supportata in Windows Forms a partire da .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Framework 4,6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli. L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità consente a un'applicazione di ignorare questo riordino quando questo comportamento è indesiderato.

In .NET Core l' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
