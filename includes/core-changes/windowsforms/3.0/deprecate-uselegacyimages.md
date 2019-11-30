---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644033"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. UseLegacyImages non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyImages`, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire dalla .NET Framework 4,8, l'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyImages` ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti ad alta risoluzione. Quando è impostato su `true`, l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%. Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.

In .NET Core, l'opzione `Switch.System.Windows.Forms.UseLegacyImages` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
