---
title: 'Procedura dettagliata: creazione di contenuto Direct3D9 per l''hosting in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1a5d70807541a0a3faf6bc99a3ced42827efd72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Procedura dettagliata: creazione di contenuto Direct3D9 per l'hosting in WPF
Questa procedura dettagliata viene illustrato come creare contenuto Direct3D9 adatto per l'hosting in un'applicazione Windows Presentation Foundation (WPF). Per ulteriori informazioni sull'hosting di contenuto Direct3D9 nelle applicazioni WPF, vedere [interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
-   Creare un progetto Direct3D9.  
  
-   Configurare il progetto Direct3D9 per l'hosting in un'applicazione WPF.  
  
 Al termine, si avrà una DLL che contiene contenuto Direct3D9 per l'utilizzo in un'applicazione WPF.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   In un secondo momento 9or DirectX SDK.  
  
## <a name="creating-the-direct3d9-project"></a>Creazione del progetto Direct3D9  
 Il primo passaggio consiste nel creare e configurare il progetto Direct3D9.  
  
#### <a name="to-create-the-direct3d9-project"></a>Per creare il progetto Direct3D9  
  
1.  Creare un nuovo progetto Win32 in C++ denominato `D3DContent`.  
  
     La creazione guidata applicazione Win32 verrà visualizzata e viene visualizzata la schermata iniziale.  
  
2.  Scegliere **Avanti**.  
  
     Viene visualizzata la schermata di impostazioni dell'applicazione.  
  
3.  Nel **tipo di applicazione:** sezione, selezionare il **DLL** opzione.  
  
4.  Scegliere **Fine**.  
  
     Il progetto D3DContent viene generato.  
  
5.  In Esplora soluzioni, fare clic sul progetto D3DContent e selezionare **proprietà**.  
  
     Il **pagine delle proprietà di D3DContent** verrà visualizzata la finestra di dialogo.  
  
6.  Selezionare il **C/C++** nodo.  
  
7.  Nel **directory di inclusione aggiuntive** , specificare il percorso di DirectX includono una cartella. Il percorso predefinito per questa cartella è %ProgramFiles%\Microsoft DirectX SDK (*versione*) \Include.  
  
8.  Fare doppio clic su di **Linker** nodo per espanderlo.  
  
9. Nel **Directory librerie aggiuntive** , specificare il percorso della cartella di librerie di DirectX. Il percorso predefinito per questa cartella è %ProgramFiles%\Microsoft DirectX SDK (*versione*) \Lib\x86.  
  
10. Selezionare il **Input** nodo.  
  
11. Nel **dipendenze aggiuntive** campo, aggiungere il `d3d9.lib` e `d3dx9.lib` file.  
  
12. In Esplora soluzioni aggiungere un nuovo file di definizione di modulo (con estensione def) denominato `D3DContent.def` al progetto.  
  
## <a name="creating-the-direct3d9-content"></a>Creazione del contenuto Direct3D9  
 Per ottenere prestazioni ottimali, il contenuto Direct3D9 necessario utilizzare impostazioni specifiche. Il codice seguente viene illustrato come creare una superficie Direct3D9 con le caratteristiche di prestazioni migliori. Per ulteriori informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### <a name="to-create-the-direct3d9-content"></a>Creare il contenuto di Direct3D9  
  
1.  In Esplora soluzioni aggiungere tre classi C++ al progetto denominato le operazioni seguenti.  
  
     `CRenderer`(con un distruttore virtuale)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  Aprire Renderer. h nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  Aprire Renderer. cpp nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  Aprire RendererManager. H nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  Aprire RendererManager. cpp nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  Aprire TriangleRenderer. H nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  Aprire TriangleRenderer. cpp nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  Aprire stdafx. h nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. Aprire DllMain. cpp nell'Editor di codice e sostituire il codice generato automaticamente con il codice seguente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. Aprire D3DContent nell'editor di codice.  
  
11. Sostituire il codice generato automaticamente con il codice seguente.  
  
    ```  
    LIBRARY "D3DContent"  
  
    EXPORTS  
  
    SetSize  
    SetAlpha  
    SetNumDesiredSamples  
    SetAdapter  
  
    GetBackBufferNoRef  
    Render  
    Destroy  
    ```  
  
12. Compilare il progetto.  
  
## <a name="next-steps"></a>Passaggi successivi  
  
-   Ospitare il contenuto Direct3D9 in un'applicazione WPF. Per ulteriori informazioni, vedere [procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.D3DImage>  
 [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
