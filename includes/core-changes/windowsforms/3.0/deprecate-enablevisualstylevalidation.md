---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721484"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Opzione di compatibilità EnableVisualStyleValidation non supportata

L' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework, l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.

In .NET Core l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione non è supportata.

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
