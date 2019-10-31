---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198457"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. EnableVisualStyleValidation non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Framework, l'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.

In .NET Core, l'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- Nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
