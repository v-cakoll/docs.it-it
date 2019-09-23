---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181847"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. UseLegacyImages non supportata

L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire dalla .NET Framework 4,8, il `Switch.System.Windows.Forms.UseLegacyImages` cambio di compatibilità ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti con valori DPI elevati. Quando è impostato `true`su, l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%. Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.

In .NET Core l' `Switch.System.Windows.Forms.UseLegacyImages` opzione non è supportata.

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
