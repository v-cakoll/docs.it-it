---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181739"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. EnableVisualStyleValidation non supportata

L' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Framework, l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico. 

In .NET Core l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione non è supportata.

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
