---
title: Ospitare contenuto Direct3D9 in WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: e65b0c59268b44abed289e54181bf0bda9355664
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742611"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Procedura dettagliata: hosting di contenuto Direct3D9 in WPF

In questa procedura dettagliata viene illustrato come ospitare il contenuto di Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).

Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

- Creare un progetto WPF per ospitare il contenuto di Direct3D9.

- Importa il contenuto di Direct3D9.

- Visualizzare il contenuto Direct3D9 usando la classe <xref:System.Windows.Interop.D3DImage>.

 Al termine, si saprà come ospitare il contenuto di Direct3D9 in un'applicazione WPF.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio.

- DirectX SDK 9 o versione successiva.

- Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF. Per altre informazioni, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: creazione di contenuto Direct3D9 per l'hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).

## <a name="creating-the-wpf-project"></a>Creazione del progetto WPF

Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.

### <a name="to-create-the-wpf-project"></a>Per creare il progetto WPF

Creare un nuovo progetto di applicazione WPF in C# un oggetto visivo denominato `D3DHost`. Per altre informazioni, vedere [Procedura dettagliata: La prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

MainWindow. XAML viene aperto in WPF Designer.

## <a name="importing-the-direct3d9-content"></a>Importazione del contenuto di Direct3D9

Il contenuto Direct3D9 viene importato da una DLL non gestita usando l'attributo `DllImport`.

### <a name="to-import-direct3d9-content"></a>Per importare il contenuto di Direct3D9

1. Aprire MainWindow.xaml.cs nell'editor di codice.

2. Sostituire il codice generato automaticamente con il codice seguente.

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>Hosting del contenuto di Direct3D9

Infine, usare la classe <xref:System.Windows.Interop.D3DImage> per ospitare il contenuto di Direct3D9.

### <a name="to-host-the-direct3d9-content"></a>Per ospitare il contenuto di Direct3D9

1. In MainWindow. xaml sostituire il codice XAML generato automaticamente con il codice XAML seguente.

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. Compilazione del progetto.

3. Copiare la DLL che contiene il contenuto di Direct3D9 nella cartella bin/debug.

4. Premere F5 per eseguire il progetto.

    Il contenuto di Direct3D9 viene visualizzato all'interno dell'applicazione WPF.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
