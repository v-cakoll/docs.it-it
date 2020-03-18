---
title: Novità di .NET Core 3.1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3.1.Learn about the new features found in .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156556"
---
# <a name="whats-new-in-net-core-31"></a>Novità di .NET Core 3.1

In questo articolo vengono descritte le novità di .NET Core 3.1.This article describes what is new in .NET Core 3.1. Questa versione contiene piccoli miglioramenti a .NET Core 3.0, concentrandosi su correzioni piccole ma importanti. La funzionalità più importante di .NET Core 3.1 è che si tratta di una versione [di supporto a lungo termine (LTS).](#long-term-support)

Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual Studio 2019 versione 16.4](https://visualstudio.microsoft.com/downloads/) per usare i progetti .NET Core 3.1. Per altre informazioni sulle novità di Visual Studio, vedere Novità di Visual Studio 2019 versione 16.4.For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4.](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164)

Visual Studio per Mac supporta e include .NET Core 3.1 in Visual Studio per Mac 8.4.

Per ulteriori informazioni sulla versione, vedere l'annuncio di [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Scarica e inizia a usare .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) su Windows, macOS o Linux.

## <a name="long-term-support"></a>Supporto a lungo termine

.NET Core 3.1 è una versione LTS con il supporto di Microsoft per i prossimi tre anni. È consigliabile spostare le app in .NET Core 3.1.It's highly recommended that you move your apps to .NET Core 3.1. Il ciclo di vita corrente di altre versioni principali è il seguente:

| Versione | Note |
| ------- | ---- |
| .NET Core 3.0 | Fine del ciclo di vita il 3 marzo 2020.     |
| .NET Core 2.2 | Fine del ciclo di vita il 23 dicembre 2019. |
| .NET Core 2.1 | Fine del ciclo di vita il 21 agosto 2021.    |

Per ulteriori informazioni, vedere i criteri di supporto di [.NET Core.](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)

## <a name="macos-apphost-and-notarization"></a>macOS appHost e notarizzazione

*Solo macOS*

A partire dal .NET Core SDK 3.1 non arizzato per macOS, l'impostazione appHost è disabilitata per impostazione predefinita. Per ulteriori informazioni, consultate la notificazione di [macOS Catalina e l'impatto sui download e sui progetti di .NET Core.](../install/macos-notarization-issues.md)

Quando l'impostazione appHost è abilitata, .NET Core genera un eseguibile Mach-O nativo durante la compilazione o la pubblicazione. L'app viene eseguita nel contesto di appHost `dotnet run` quando viene eseguita dal codice sorgente con il comando o avviando direttamente l'eseguibile Mach-O.

Senza appHost, l'unico modo in cui un utente `dotnet <filename.dll>` può [avviare](../deploying/index.md#publish-runtime-dependent) un'app dipendente dal runtime è con il comando. Un appHost viene sempre creato quando si pubblica l'app [indipendente.](../deploying/index.md#publish-self-contained)

Puoi configurare appHost a livello di progetto o attivare `dotnet` o `-p:UseAppHost` disattivare l'appHost per un comando specifico con il parametro:

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

Per ulteriori informazioni `UseAppHost` sull'impostazione, vedere [Proprietà MSBuild per Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

## <a name="windows-forms"></a>Windows Form

*Solo Windows*

> [!WARNING]
> Sono state apportate modifiche di rilievo in Windows Form.There are breaking changes in Windows Forms.

Controlli legacy sono stati inclusi in Windows Form che sono stati non disponibili nella casella degli strumenti di progettazione di Visual Studio per qualche tempo. Questi sono stati sostituiti con nuovi controlli in .NET Framework 2.0. Questi sono stati rimossi da Desktop SDK per .NET Core 3.1.

| Controllo rimosso | Sostituzione consigliata | API associate rimosse |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | Datagridcell<br/>Datagridrow<br/>DataGridTableCollection<br/>Datagridcolumncollection<br/>Datagridtablestyle<br/>Datagridcolumnstyle<br/>Oggetto DataGridLineStyle<br/>DataGridParentRowsLabel (Etichetta)DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>Datagridtextbox<br/>Gridcolumnstylescollection<br/>Gridtablestylescollection<br/>HitTestType (Tipo di HitTest) |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAspetto |
| Toolbarbutton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign (Riga di dialogo) |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | Menuitemcollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

È consigliabile aggiornare le applicazioni a .NET Core 3.1 e passare ai controlli di sostituzione. La sostituzione dei controlli è un processo semplice, essenzialmente "trova e sostituisci" sul tipo.

## <a name="ccli"></a>C++/CLI

*Solo Windows*

È stato aggiunto il supporto per la creazione di progetti in C, c/CLI, noti anche come progetti "gestiti in C). I file binari prodotti da questi progetti sono compatibili con .NET Core 3.0 e versioni successive.

Per aggiungere il supporto per il linguaggio C.NET/CLI in Visual Studio 2019 versione 16.4, installare lo sviluppo desktop con il carico di lavoro di [C.](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads) Questo carico di lavoro aggiunge due modelli a Visual Studio:This workload adds two templates to Visual Studio:

- CLR Class Library (.NET Core)
- CLR Empty Project (.NET Core)

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le modifiche di rilievo tra .NET Core 3.0 e 3.1.Review the breaking changes between .NET Core 3.0 and 3.1.](../compatibility/3.0-3.1.md)
- [Esaminare le modifiche di rilievo in .NET Core 3.1 per le applicazioni Windows Form.Review the breaking changes in .NET Core 3.1 for Windows Forms apps.](../compatibility/winforms.md#net-core-31)
