---
ms.openlocfilehash: e1c55eab0b968daab7322350e201b49149e63215
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721160"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata

L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità è supportata in Windows Forms in .NET Framework 4,6 e versioni successive, ma non è supportata in Windows Forms a partire da .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework 4,6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli. L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità consente a un'applicazione di ignorare questo riordino quando questo comportamento è indesiderato.

In .NET Core l' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- Nessuno

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
