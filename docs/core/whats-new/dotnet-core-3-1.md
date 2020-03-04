---
title: Novità di .NET Core 3.1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3,1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156556"
---
# <a name="whats-new-in-net-core-31"></a>Novità di .NET Core 3.1

Questo articolo descrive le novità di .NET Core 3,1. Questa versione contiene miglioramenti secondari a .NET Core 3,0, con particolare attenzione alle piccole, ma importanti correzioni. La funzionalità più importante di .NET Core 3,1 è che si tratta di una versione di [supporto a lungo termine (LTS)](#long-term-support) .

Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual studio 2019 versione 16,4](https://visualstudio.microsoft.com/downloads/) per lavorare con i progetti .net core 3,1. Per ulteriori informazioni sulle novità di Visual Studio, vedere Novità di [Visual studio 2019 versione 16,4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).

Visual Studio per Mac supporta inoltre e include .NET Core 3,1 in Visual Studio per Mac 8,4.

Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Scaricare e iniziare a usare .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) in Windows, MacOS o Linux.

## <a name="long-term-support"></a>Supporto a lungo termine

.NET Core 3,1 è una versione LTS con supporto Microsoft per i prossimi tre anni. Si consiglia vivamente di spostare le app in .NET Core 3,1. Il ciclo di vita corrente di altre versioni principali è il seguente:

| Versione | Note |
| ------- | ---- |
| .NET Core 3.0 | Fine vita il 3 marzo 2020.     |
| .NET Core 2.2 | Fine vita il 23 dicembre 2019. |
| .NET Core 2.1 | Fine del ciclo di vita del 21 agosto 2021.    |

Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="macos-apphost-and-notarization"></a>appHost e autenticazione macOS

*solo macOS*

A partire dalla .NET Core SDK autenticata 3,1 per macOS, l'impostazione appHost è disabilitata per impostazione predefinita. Per altre informazioni, vedere [la pagina relativa all'autenticazione di MacOS Catalina e l'effetto sui download e sui progetti di .NET Core](../install/macos-notarization-issues.md).

Quando è abilitata l'impostazione appHost, .NET Core genera un eseguibile nativo di Mach-O durante la compilazione o la pubblicazione. L'app viene eseguita nel contesto di appHost quando viene eseguita dal codice sorgente con il comando `dotnet run` o avviando direttamente il file eseguibile di Mach-O.

Senza appHost, l'unico modo in cui un utente può avviare un'app [dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) è con il comando `dotnet <filename.dll>`. Quando si pubblica l'app [autonoma](../deploying/index.md#publish-self-contained), viene sempre creato un APPHOST.

È possibile configurare appHost a livello di progetto o impostare il appHost per un comando `dotnet` specifico con il parametro `-p:UseAppHost`:

- File di progetto

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Parametro della riga di comando

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Per ulteriori informazioni sull'impostazione di `UseAppHost`, vedere [Proprietà MSBuild per Microsoft. NET. SDK](../project-sdk/msbuild-props.md#useapphost).

## <a name="windows-forms"></a>Windows Form

*Solo Windows*

> [!WARNING]
> Sono state apportate modifiche di rilievo in Windows Forms.

I controlli legacy erano inclusi in Windows Forms che non erano disponibili nella casella degli strumenti di progettazione di Visual Studio per un certo periodo di tempo. Questi sono stati sostituiti con nuovi controlli nella .NET Framework 2,0. Questi elementi sono stati rimossi da desktop SDK per .NET Core 3,1.

| Rimozione del controllo | Sostituzione consigliata | API associate rimosse |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

Si consiglia di aggiornare le applicazioni a .NET Core 3,1 e di passare ai controlli sostitutivi. La sostituzione dei controlli è un processo semplice, sostanzialmente "trova e Sostituisci" sul tipo.

## <a name="ccli"></a>C++/CLI

*Solo Windows*

È stato aggiunto il supporto per C++la creazione di progetti/CLI (noti C++anche come "gestiti"). I file binari prodotti da questi progetti sono compatibili con .NET Core 3,0 e versioni successive.

Per aggiungere il supporto C++per/CLI in Visual Studio 2019 versione 16,4, installare lo [sviluppo di C++ applicazioni desktop con il carico di lavoro](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads). Questo carico di lavoro aggiunge due modelli a Visual Studio:

- Libreria di classi CLR (.NET Core)
- Progetto CLR vuoto (.NET Core)

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le modifiche di rilievo tra .NET Core 3,0 e 3,1.](../compatibility/3.0-3.1.md)
- [Esaminare le modifiche di rilievo apportate in .NET Core 3,1 per le app Windows Forms.](../compatibility/winforms.md#net-core-31)
