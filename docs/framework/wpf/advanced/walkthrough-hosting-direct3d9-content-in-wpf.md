---
title: 'Procedura dettagliata: hosting di contenuto Direct3D9 in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 3b215c0eead8c5fc28b477b81f75c39b5c946302
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546172"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Procedura dettagliata: hosting di contenuto Direct3D9 in WPF
Questa procedura dettagliata viene illustrato come ospitare contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
-   Creare un progetto WPF per ospitare il contenuto Direct3D9.  
  
-   Importare il contenuto Direct3D9.  
  
-   Visualizzare il contenuto Direct3D9 utilizzando la <xref:System.Windows.Interop.D3DImage> classe.  
  
 Al termine, si saprà come ospitare contenuto Direct3D9 in un'applicazione WPF.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 o versione successiva.  
  
-   Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF. Per ulteriori informazioni, vedere [interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: creazione di contenuto Direct3D9 per l'Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Creazione del progetto WPF  
 Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.  
  
#### <a name="to-create-the-wpf-project"></a>Per creare il progetto WPF  
  
-   Creare un nuovo progetto di applicazione WPF in Visual c# denominato `D3DHost`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     MainWindow. XAML viene aperto nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>L'importazione del contenuto Direct3D9  
 Per importare il contenuto di Direct3D9 da una DLL non gestita usando il `DllImport` attributo.  
  
#### <a name="to-import-direct3d9-content"></a>Per importare il contenuto Direct3D9  
  
1.  Aprire MainWindow.xaml.cs nell'Editor di codice.  
  
2.  Sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Ospitare il contenuto Direct3D9  
 Infine, utilizzare la <xref:System.Windows.Interop.D3DImage> classe per ospitare il contenuto Direct3D9.  
  
#### <a name="to-host-the-direct3d9-content"></a>Per ospitare il contenuto Direct3D9  
  
1.  In MainWindow. XAML, sostituire il codice XAML generato automaticamente con il seguente codice XAML.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Compilare il progetto.  
  
3.  Copiare la DLL che contiene il contenuto Direct3D9 nella cartella bin/Debug.  
  
4.  Premere F5 per eseguire il progetto.  
  
     Il contenuto Direct3D9 viene visualizzato all'interno dell'applicazione WPF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.D3DImage>  
 [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
