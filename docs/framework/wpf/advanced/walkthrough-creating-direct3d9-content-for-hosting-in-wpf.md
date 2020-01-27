---
title: Crea contenuto Direct3D9 per l'hosting
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 847ee74da5b295c2c9d3824b3df74f94bc98a4db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727913"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Procedura dettagliata: creazione di contenuto Direct3D9 per l'hosting in WPF
In questa procedura dettagliata viene illustrato come creare contenuto Direct3D9 adatto per l'hosting in un'applicazione Windows Presentation Foundation (WPF). Per ulteriori informazioni sull'hosting di contenuto Direct3D9 nelle applicazioni WPF, vedere [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).

 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

- Creare un progetto Direct3D9.

- Configurare il progetto Direct3D9 per l'hosting in un'applicazione WPF.

 Al termine, si disporrà di una DLL che contiene contenuto Direct3D9 per l'uso in un'applicazione WPF.

## <a name="prerequisites"></a>Prerequisiti
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2010.

- DirectX SDK 9 o versione successiva.

## <a name="creating-the-direct3d9-project"></a>Creazione del progetto Direct3D9
 Il primo passaggio consiste nel creare e configurare il progetto Direct3D9.

#### <a name="to-create-the-direct3d9-project"></a>Per creare il progetto Direct3D9

1. Creare un nuovo progetto Win32 in C++ denominato `D3DContent`.

     Si apre la creazione guidata applicazione Win32 e viene visualizzata la schermata iniziale.

2. Scegliere **Avanti**.

     Viene visualizzata la schermata Impostazioni applicazione.

3. Nella sezione **tipo di applicazione:** selezionare l'opzione **dll** .

4. Scegliere **Fine**.

     Viene generato il progetto D3DContent.

5. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto D3DContent e scegliere **Proprietà**.

     Verrà visualizzata la finestra di dialogo **pagine delle proprietà di D3DContent** .

6. Selezionare il nodo **CC++ /** .

7. Nel campo **directory di inclusione aggiuntive** specificare il percorso della cartella di inclusione DirectX. Il percorso predefinito per questa cartella è%Programmi%\Microsoft DirectX SDK (*Version*) \Include.

8. Fare doppio clic sul nodo **linker** per espanderlo.

9. Nel campo **Directory librerie aggiuntive** specificare il percorso della cartella librerie DirectX. Il percorso predefinito per questa cartella è%Programmi%\Microsoft DirectX SDK (*Version*) \Lib\x86.

10. Selezionare il nodo di **input** .

11. Nel campo **dipendenze aggiuntive** aggiungere i file di `d3d9.lib` e `d3dx9.lib`.

12. In Esplora soluzioni aggiungere un nuovo file di definizione del modulo (con estensione def) denominato `D3DContent.def` al progetto.

## <a name="creating-the-direct3d9-content"></a>Creazione del contenuto di Direct3D9
 Per ottenere prestazioni ottimali, il contenuto di Direct3D9 deve usare impostazioni particolari. Nel codice seguente viene illustrato come creare una superficie Direct3D9 con le caratteristiche di prestazioni ottimali. Per ulteriori informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>Per creare il contenuto di Direct3D9

1. Utilizzando Esplora soluzioni, aggiungere tre C++ classi al progetto denominate quanto segue.

     `CRenderer` (con distruttore virtuale)

     `CRendererManager`

     `CTriangleRenderer`

2. Aprire Renderer. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. Aprire Renderer. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. Aprire RendererManager. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. Aprire RendererManager. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. Aprire TriangleRenderer. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. Aprire TriangleRenderer. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. Aprire stdafx. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. Aprire DllMain. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. Aprire D3DContent. def nell'editor di codice.

11. Sostituire il codice generato automaticamente con il codice seguente.

    ```cpp
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

12. Compilazione del progetto.

## <a name="next-steps"></a>Passaggi successivi

- Ospitare il contenuto di Direct3D9 in un'applicazione WPF. Per ulteriori informazioni, vedere [procedura dettagliata: hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.D3DImage>
- [Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
