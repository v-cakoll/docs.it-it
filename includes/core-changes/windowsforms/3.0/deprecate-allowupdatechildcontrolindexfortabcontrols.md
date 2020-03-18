---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937054"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata

L'opzione `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` di compatibilità è supportata in Windows Form in .NET Framework 4.6 e versioni successive, ma non in Windows Form a partire da .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework 4.6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli. L'opzione `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` di compatibilità consente a un'applicazione di ignorare questo riordinamento quando questo comportamento non è auspicabile.

In .NET Core `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` l'opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
