---
title: 'Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 07cfa5bed6e5af131a60a303f0702f18413043e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007121"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF
Questa procedura dettagliata viene illustrato come ospitare contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
- Creare un progetto WPF per ospitare il contenuto Direct3D9.  
  
- Importare il contenuto Direct3D9.  
  
- Visualizzazione di contenuto Direct3D9 mediante il <xref:System.Windows.Interop.D3DImage> classe.  
  
 Al termine, si saprà come ospitare contenuto Direct3D9 in un'applicazione WPF.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
- Visual Studio.  
  
- DirectX SDK 9 o versione successiva.  
  
- Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF. Per altre informazioni, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: Creazione di contenuto Direct3D9 per l'Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Creazione del progetto WPF  
 Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.  
  
#### <a name="to-create-the-wpf-project"></a>Per creare il progetto WPF  
  
- Creare un nuovo progetto di applicazione WPF in Visual c# denominato `D3DHost`. Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
     MainWindow. XAML viene aperto nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>L'importazione di contenuto Direct3D9  
 Per importare il contenuto Direct3D9 da una DLL non gestita utilizzando il `DllImport` attributo.  
  
#### <a name="to-import-direct3d9-content"></a>Per importare il contenuto Direct3D9  
  
1. Aprire MainWindow.xaml.cs nell'Editor del codice.  
  
2. Sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Hosting di contenuto Direct3D9  
 Usare infine il <xref:System.Windows.Interop.D3DImage> classe per ospitare il contenuto Direct3D9.  
  
#### <a name="to-host-the-direct3d9-content"></a>Per ospitare il contenuto Direct3D9  
  
1. In MainWindow. XAML, sostituire il XAML generato automaticamente con il XAML seguente.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2. Compilare il progetto.  
  
3. Copiare la DLL che contiene il contenuto Direct3D9 alla cartella bin/Debug.  
  
4. Premere F5 per eseguire il progetto.  
  
     Il contenuto Direct3D9 viene visualizzato all'interno dell'applicazione WPF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
