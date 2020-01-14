---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937054"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` è supportata in Windows Forms in .NET Framework 4,6 e versioni successive, ma non è supportata in Windows Forms a partire da .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

In .NET Framework 4,6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli. Il `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità consente a un'applicazione di ignorare questo riordino quando questo comportamento è indesiderato.

In .NET Core, l'opzione `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
