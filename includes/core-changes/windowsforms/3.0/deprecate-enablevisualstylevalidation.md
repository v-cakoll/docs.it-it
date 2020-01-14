---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937087"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>Opzione di compatibilità EnableVisualStyleValidation non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

In .NET Framework, l'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.

In .NET Core, l'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata.

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
