---
title: 'Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 2c31c044aa50a74255a61da1675037ab3d09f615
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053460"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF

In questa procedura dettagliata viene illustrato come ospitare il contenuto di Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).

Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

- Creare un progetto WPF per ospitare il contenuto di Direct3D9.

- Importa il contenuto di Direct3D9.

- Visualizzare il contenuto Direct3D9 usando la <xref:System.Windows.Interop.D3DImage> classe.

 Al termine, si saprà come ospitare il contenuto di Direct3D9 in un'applicazione WPF.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio.

- DirectX SDK 9 o versione successiva.

- Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF. Per ulteriori informazioni, vedere l' [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)in WPF.

## <a name="creating-the-wpf-project"></a>Creazione del progetto WPF

Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.

### <a name="to-create-the-wpf-project"></a>Per creare il progetto WPF

Creare un nuovo progetto di applicazione WPF nell' C# oggetto `D3DHost`visivo denominato. Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione](../getting-started/walkthrough-my-first-wpf-desktop-application.md)desktop WPF.

MainWindow. XAML viene aperto in [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

## <a name="importing-the-direct3d9-content"></a>Importazione del contenuto di Direct3D9

Il contenuto Direct3D9 viene importato da una dll non gestita usando l' `DllImport` attributo.

### <a name="to-import-direct3d9-content"></a>Per importare il contenuto di Direct3D9

1. Aprire MainWindow.xaml.cs nell'editor di codice.

2. Sostituire il codice generato automaticamente con il codice seguente.

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>Hosting del contenuto di Direct3D9

Infine, usare la <xref:System.Windows.Interop.D3DImage> classe per ospitare il contenuto di Direct3D9.

### <a name="to-host-the-direct3d9-content"></a>Per ospitare il contenuto di Direct3D9

1. In MainWindow. xaml sostituire il codice XAML generato automaticamente con il codice XAML seguente.

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. Compilare il progetto.

3. Copiare la DLL che contiene il contenuto di Direct3D9 nella cartella bin/debug.

4. Premere F5 per eseguire il progetto.

    Il contenuto di Direct3D9 viene visualizzato all'interno dell'applicazione WPF.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
