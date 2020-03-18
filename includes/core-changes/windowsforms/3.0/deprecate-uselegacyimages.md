---
ms.openlocfilehash: 3eab49acd3eaa5b6d5802af5f4e6f0fe2699ee97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937046"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>Opzione di compatibilità UseLegacyImages non supportata

L'opzione `Switch.System.Windows.Forms.UseLegacyImages` di compatibilità, introdotta in .NET Framework 4.8, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework `Switch.System.Windows.Forms.UseLegacyImages` 4.8. Se impostato `true`su , l'opzione consente all'utente di ripristinare il ridimensionamento delle immagini legacy su schermi DPI elevati la cui scala è impostata su un valore superiore al 100%. Per altre informazioni, vedere Note sulla versione di .NET Framework 4.8 su GitHub.For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.

In .NET Core `Switch.System.Windows.Forms.UseLegacyImages` l'opzione non è supportata.

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
