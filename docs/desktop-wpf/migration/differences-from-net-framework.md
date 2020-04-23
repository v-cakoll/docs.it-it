---
title: Differenze tra .NET Framework e .NET Core
description: Vengono descritte le differenze tra l'implementazione di .NET Framework di Windows Presentation Foundation (WPF) e WPF .NET Core. Quando esegui la migrazione dell'app, devi considerare queste incompatibilità.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82072207"
---
# <a name="differences-in-wpf"></a>Differenze in WPF

In questo articolo vengono descritte le differenze tra Windows Presentation Foundation (WPF) in .NET Core e .NET Framework. WPF per .NET Core è un [framework open source](https://github.com/dotnet/wpf) con un cloud dal codice sorgente di WPF per .NET Framework originale.

Esistono alcune funzionalità di .NET Framework non supportate da .NET Core. Per ulteriori informazioni sulle tecnologie non supportate, vedere [Tecnologie .NET Framework non disponibili in .NET Core](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Progetti in stile SDK

.NET Core utilizza file di progetto di tipo SDK. Questi file di progetto sono diversi dai tradizionali file di progetto .NET Framework gestiti da Visual Studio.These project files are different from the traditional .NET Framework project files managed by Visual Studio. Per eseguire la migrazione delle app WPF di .NET Framework a .NET Core, è necessario convertire i progetti. Per altre informazioni, vedere Eseguire la migrazione di app WPF a .NET Core 3.0.For more information, see [Migrate WPF apps to .NET Core 3.0.](convert-project-from-net-framework.md)

## <a name="nuget-package-references"></a>Riferimenti al pacchetto NuGet

Se l'app .NET Framework elenca le dipendenze NuGet in [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) un file *packages.config,* eseguire la migrazione al formato seguente:

1. In Visual Studio aprire il riquadro **Esplora soluzioni.**
1. Nel progetto WPF fare clic con il pulsante destro del mouse su **packages.config** > **Migrate packages.config a PackageReference**.

![Aggiornamento a PackageReferenceUpgrading to PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Apparirà una finestra di dialogo che mostra le dipendenze NuGet di primo livello calcolate e chiede quali altri pacchetti NuGet devono essere promossi al livello superiore. Selezionare **OK** e il file *packages.config* `<PackageReference>` verrà rimosso dal progetto e gli elementi verranno aggiunti al file di progetto.

Quando il `<PackageReference>`progetto utilizza , i pacchetti non vengono archiviati localmente in una cartella *Pacchetti,* vengono archiviati globalmente. Aprire il file di `<Analyzer>` progetto e rimuovere tutti gli elementi che fanno riferimento alla cartella *pacchetti.* Questi analizzatori vengono inclusi automaticamente con i riferimenti al pacchetto NuGet.These analyzers are automatically included with the NuGet package references.

## <a name="code-access-security"></a>Sicurezza dall'accesso di codice

La sicurezza dall'accesso di codice non è supportata da .NET Core o WPF per .NET Core.Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core. Tutte le funzionalità correlate a CAS vengono trattate presupponendo la massima attendibilità. WPF per .NET Core rimuove il codice correlato a CAS. La superficie API pubblica di questi tipi esiste ancora per garantire che le chiamate a questi tipi abbiano esito positivo.

I tipi correlati a CAS definiti pubblicamente sono stati spostati all'esterno degli assembly WPF e agli assembly della libreria .NET Core. Gli assembly WPFWPF hanno l'inoltro dei tipi impostato sulla nuova posizione dei tipi spostati.

| Assemblaggio di origine | Assemblaggio di destinazione | Type                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Per ridurre al minimo l'attrito di conversione, il `XamlAccessLevel` tipo è stata mantenuta la funzionalità per l'archiviazione e il recupero delle informazioni relative alle proprietà seguenti.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni su come eseguire il porting di un'app WPF di .NET Framework in .NET Core.Learn how to port a .NET Framework WPF app to .NET Core.](convert-project-from-net-framework.md)
