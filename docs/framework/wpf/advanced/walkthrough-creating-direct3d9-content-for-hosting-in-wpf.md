---
title: "Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF"
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: e1cb5832ec6e383d1ee183b6bc9a86745ecc207c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605847"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Procedura dettagliata: Creazione di contenuto Direct3D9 per l'hosting in WPF
Questa procedura dettagliata viene illustrato come creare contenuto Direct3D9 adatto per l'hosting in un'applicazione Windows Presentation Foundation (WPF). Per ulteriori informazioni sull'hosting di contenuto Direct3D9 in applicazioni WPF, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md).

 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

- Creare un progetto Direct3D9.

- Configurare il progetto Direct3D9 per l'hosting in un'applicazione WPF.

 Al termine, si avrà una DLL che contiene contenuto Direct3D9 per l'uso in un'applicazione WPF.

## <a name="prerequisites"></a>Prerequisiti
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2010.

- DirectX SDK 9 o versione successiva.

## <a name="creating-the-direct3d9-project"></a>Creazione del progetto Direct3D9
 Il primo passaggio è per creare e configurare il progetto Direct3D9.

#### <a name="to-create-the-direct3d9-project"></a>Per creare il progetto Direct3D9

1. Creare un nuovo progetto Win32 in C++ denominato `D3DContent`.

     La creazione guidata applicazione Win32 apre e Visualizza la schermata iniziale.

2. Scegliere **Avanti**.

     Viene visualizzata la schermata impostazioni dell'applicazione.

3. Nel **tipo di applicazione:** selezionare la **DLL** opzione.

4. Scegliere **Fine**.

     Il progetto D3DContent viene generato.

5. In Esplora soluzioni fare clic sul progetto D3DContent e selezionare **proprietà**.

     Il **pagine delle proprietà D3DContent** verrà visualizzata la finestra di dialogo.

6. Selezionare il **C/C++** nodo.

7. Nel **directory di inclusione aggiuntive** , specificare il percorso di DirectX sono inclusi cartelle. Il percorso predefinito per questa cartella è %ProgramFiles%\Microsoft DirectX SDK (*versione*) \Include.

8. Fare doppio clic il **Linker** nodo per espanderlo.

9. Nel **Directory librerie aggiuntive** campo, specificare il percorso della cartella di librerie DirectX. Il percorso predefinito per questa cartella è %ProgramFiles%\Microsoft DirectX SDK (*versione*) \Lib\x86.

10. Selezionare il **Input** nodo.

11. Nel **dipendenze aggiuntive** campo, aggiungere il `d3d9.lib` e `d3dx9.lib` file.

12. In Esplora soluzioni aggiungere un nuovo file di definizione di modulo (def) denominato `D3DContent.def` al progetto.

## <a name="creating-the-direct3d9-content"></a>Creazione di contenuto Direct3D9
 Per ottenere prestazioni ottimali, il contenuto Direct3D9 necessario utilizzare impostazioni particolare. Il codice seguente viene illustrato come creare una superficie Direct3D9 con le caratteristiche di prestazioni migliori. Per altre informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità di WPF e Direct3D9](performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>Per creare il contenuto di Direct3D9

1. In Esplora soluzioni aggiungere tre classi C++ al progetto denominato nel modo seguente.

     `CRenderer` (con un distruttore virtuale)

     `CRendererManager`

     `CTriangleRenderer`

2. Aprire Renderer. h nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. Aprire Renderer. cpp nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. Aprire RendererManager. H nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. Aprire RendererManager. cpp nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. Aprire TriangleRenderer. H nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. Aprire TriangleRenderer. cpp nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. Aprire file stdafx. h nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. Aprire DllMain. cpp nell'Editor del codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. Aprire D3DContent nell'editor del codice.

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

- Ospitare il contenuto Direct3D9 in un'applicazione WPF. Per altre informazioni, vedere [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
