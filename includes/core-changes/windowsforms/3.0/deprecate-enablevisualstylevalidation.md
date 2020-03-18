---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937087"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>EnableVisualStyleValidation opzione di compatibilità non supportata

L'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` di compatibilità non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework `Switch.System.Windows.Forms.EnableVisualStyleValidation` l'opzione di compatibilità consente a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in formato numerico.

In .NET Core `Switch.System.Windows.Forms.EnableVisualStyleValidation` l'opzione non è supportata.

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
