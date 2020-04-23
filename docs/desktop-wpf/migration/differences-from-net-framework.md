---
title: Differenze tra .NET Framework e .NET Core
description: Vengono descritte le differenze tra l'implementazione .NET Framework di Windows Presentation Foundation (WPF) e .NET Core WPF. Quando si esegue la migrazione dell'app, è necessario prendere in considerazione queste incompatibilità.
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

Questo articolo descrive le differenze tra Windows Presentation Foundation (WPF) in .NET Core e .NET Framework. WPF per .NET Core è un [Framework open source](https://github.com/dotnet/wpf) con fork da WPF originale per .NET Framework codice sorgente.

Alcune funzionalità di .NET Framework non sono supportate da .NET Core. Per ulteriori informazioni sulle tecnologie non supportate, vedere [.NET Framework tecnologie non disponibili in .NET Core](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Progetti in stile SDK

.NET Core usa i file di progetto in stile SDK. Questi file di progetto sono diversi dai file di progetto .NET Framework tradizionali gestiti da Visual Studio. Per eseguire la migrazione delle app .NET Framework WPF a .NET Core, è necessario convertire i progetti. Per altre informazioni, vedere [eseguire la migrazione di app WPF a .NET Core 3,0](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>Riferimenti al pacchetto NuGet

Se l'app .NET Framework elenca le dipendenze NuGet in un file *packages. config* , eseguire [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) la migrazione nel formato:

1. In Visual Studio aprire il riquadro **Esplora soluzioni** .
1. Nel progetto WPF, fare clic con il pulsante destro del mouse su **packages. config** > **migrate Packages. config a PackageReference**.

![Aggiornamento a PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Verrà visualizzata una finestra di dialogo che mostra le dipendenze NuGet di primo livello calcolate e chiede quali altri pacchetti NuGet devono essere promossi al livello principale. Selezionare **OK** e il file *packages. config* verrà rimosso dal progetto e `<PackageReference>` gli elementi verranno aggiunti al file di progetto.

Quando il progetto usa `<PackageReference>`, i pacchetti non vengono archiviati localmente in una cartella di *pacchetti* , vengono archiviati a livello globale. Aprire il file di progetto e rimuovere `<Analyzer>` tutti gli elementi che fanno riferimento alla cartella *pacchetti* . Questi analizzatori vengono inclusi automaticamente con i riferimenti ai pacchetti NuGet.

## <a name="code-access-security"></a>Sicurezza dall'accesso di codice

La sicurezza dall'accesso di codice (CAS) non è supportata da .NET Core o WPF per .NET Core. Tutte le funzionalità correlate all'autorità di certificazione vengono gestite in base al presupposto dell'attendibilità totale. WPF per .NET Core rimuove il codice correlato all'autorità di certificazione. La superficie dell'API pubblica di questi tipi esiste ancora per garantire l'esito positivo delle chiamate in questi tipi.

I tipi correlati alle CA definite pubblicamente sono stati spostati dagli assembly WPF e negli assembly della libreria .NET di base. Per gli assembly WPF il tipo viene impostato sulla nuova posizione dei tipi spostati.

| Assembly di origine | Assembly di destinazione | Type                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System. Security. Permissions. dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System. Security. Permissions. dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System. Windows. Extension. dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Per ridurre al minimo l'attrito del porting, la funzionalità per l'archiviazione e il recupero delle informazioni correlate alle proprietà seguenti è `XamlAccessLevel` stata mantenuta nel tipo.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni su come trasferire un'app .NET Framework WPF a .NET Core.](convert-project-from-net-framework.md)
