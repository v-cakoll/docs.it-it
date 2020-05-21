---
ms.openlocfilehash: c980b0c0be9f4d6a529baa0743dec9ac16ca0d7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721721"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>Opzione di compatibilità UseLegacyImages non supportata

L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4,8, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

A partire dalla .NET Framework 4,8, il `Switch.System.Windows.Forms.UseLegacyImages` cambio di compatibilità ha risolto i possibili problemi di scalabilità delle immagini negli scenari ClickOnce negli ambienti con valori DPI elevati. Quando è impostato su `true` , l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi a DPI elevato la cui scala è impostata su un valore maggiore del 100%. Per ulteriori informazioni, vedere le [Note sulla versione di .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) su GitHub.

In .NET Core l' `Switch.System.Windows.Forms.UseLegacyImages` opzione non è supportata.

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
