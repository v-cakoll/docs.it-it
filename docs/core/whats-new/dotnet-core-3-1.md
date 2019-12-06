---
title: Novità di .NET Core 3,1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3,1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 08ae824b79ba6a1ff5a92a0b4306eabe5ccadfd2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838323"
---
# <a name="whats-new-in-net-core-31"></a>Novità di .NET Core 3,1

Questo articolo descrive le novità di .NET Core 3,1. Questa versione contiene miglioramenti secondari a .NET Core 3,0, con particolare attenzione alle piccole, ma importanti correzioni. La funzionalità più importante di .NET Core 3,1 è che si tratta di una versione di [supporto a lungo termine (LTS)](#long-term-support) .

Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual studio 2019 16,4](https://visualstudio.microsoft.com/downloads/) per lavorare con i progetti .net core 3,1. Per ulteriori informazioni sulle novità di Visual Studio, vedere il Blog di [Visual Studio](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/).

Visual Studio per Mac supporta inoltre e include .NET Core 3,1, nel canale di anteprima Visual Studio per Mac 8,4. È necessario scegliere il canale di anteprima per usare .NET Core 3,1.

Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Scaricare e iniziare a usare .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) in Windows, MacOS o Linux.

## <a name="long-term-support"></a>Supporto a lungo termine

.NET Core 3,1 è una versione LTS con supporto Microsoft per i prossimi tre anni. Si consiglia vivamente di spostare le app in .NET Core 3,1. Il ciclo di vita corrente di altre versioni principali è il seguente:

| Release | Nota |
| ------- | ---- |
| .NET Core 3.0 | Fine vita il 3 marzo 2020.     |
| .NET Core 2.2 | Fine vita il 23 dicembre 2019. |
| .NET Core 2.1 | Fine del ciclo di vita del 21 agosto 2021.    |

Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

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

Per aggiungere il supporto C++per/CLI in Visual Studio 2019 16,4, installare lo [sviluppo di C++ applicazioni desktop con il carico di lavoro](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads). Questo carico di lavoro aggiunge due modelli a Visual Studio:

- Libreria di classi CLR (.NET Core)
- Progetto CLR vuoto (.NET Core)

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le modifiche di rilievo tra .NET Core 3,0 e 3,1.](../compatibility/3.0-3.1.md)
- [Esaminare le modifiche di rilievo tra .NET Framework e .NET Core 3,0 per le app Windows Forms.](../porting/winforms-breaking-changes.md)
