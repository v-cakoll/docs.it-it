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
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="fc1e1-102">Procedura dettagliata: creazione di contenuto Direct3D9 per l'hosting in WPF</span><span class="sxs-lookup"><span data-stu-id="fc1e1-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="fc1e1-103">In questa procedura dettagliata viene illustrato come creare contenuto Direct3D9 adatto per l'hosting in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="fc1e1-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="fc1e1-104">Per ulteriori informazioni sull'hosting di contenuto Direct3D9 nelle applicazioni WPF, vedere [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="fc1e1-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="fc1e1-105">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc1e1-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="fc1e1-106">Creare un progetto Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="fc1e1-107">Configurare il progetto Direct3D9 per l'hosting in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="fc1e1-108">Al termine, si disporrà di una DLL che contiene contenuto Direct3D9 per l'uso in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc1e1-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fc1e1-109">Prerequisites</span></span>
 <span data-ttu-id="fc1e1-110">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc1e1-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="fc1e1-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="fc1e1-112">DirectX SDK 9 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="fc1e1-113">Creazione del progetto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc1e1-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="fc1e1-114">Il primo passaggio consiste nel creare e configurare il progetto Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="fc1e1-115">Per creare il progetto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc1e1-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="fc1e1-116">Creare un nuovo progetto Win32 in C++ denominato `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="fc1e1-117">Si apre la creazione guidata applicazione Win32 e viene visualizzata la schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="fc1e1-118">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-118">Click **Next**.</span></span>

     <span data-ttu-id="fc1e1-119">Viene visualizzata la schermata Impostazioni applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="fc1e1-120">Nella sezione **tipo di applicazione:** selezionare l'opzione **dll** .</span><span class="sxs-lookup"><span data-stu-id="fc1e1-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="fc1e1-121">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-121">Click **Finish**.</span></span>

     <span data-ttu-id="fc1e1-122">Viene generato il progetto D3DContent.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="fc1e1-123">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto D3DContent e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="fc1e1-124">Verrà visualizzata la finestra di dialogo **pagine delle proprietà di D3DContent** .</span><span class="sxs-lookup"><span data-stu-id="fc1e1-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="fc1e1-125">Selezionare il nodo **CC++ /** .</span><span class="sxs-lookup"><span data-stu-id="fc1e1-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="fc1e1-126">Nel campo **directory di inclusione aggiuntive** specificare il percorso della cartella di inclusione DirectX.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="fc1e1-127">Il percorso predefinito per questa cartella è%Programmi%\Microsoft DirectX SDK (*Version*) \Include.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="fc1e1-128">Fare doppio clic sul nodo **linker** per espanderlo.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="fc1e1-129">Nel campo **Directory librerie aggiuntive** specificare il percorso della cartella librerie DirectX.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="fc1e1-130">Il percorso predefinito per questa cartella è%Programmi%\Microsoft DirectX SDK (*Version*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="fc1e1-131">Selezionare il nodo di **input** .</span><span class="sxs-lookup"><span data-stu-id="fc1e1-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="fc1e1-132">Nel campo **dipendenze aggiuntive** aggiungere i file di `d3d9.lib` e `d3dx9.lib`.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="fc1e1-133">In Esplora soluzioni aggiungere un nuovo file di definizione del modulo (con estensione def) denominato `D3DContent.def` al progetto.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="fc1e1-134">Creazione del contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc1e1-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="fc1e1-135">Per ottenere prestazioni ottimali, il contenuto di Direct3D9 deve usare impostazioni particolari.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="fc1e1-136">Nel codice seguente viene illustrato come creare una superficie Direct3D9 con le caratteristiche di prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="fc1e1-137">Per ulteriori informazioni, vedere [considerazioni sulle prestazioni per l'interoperabilità Direct3D9 e WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="fc1e1-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="fc1e1-138">Per creare il contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="fc1e1-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="fc1e1-139">Utilizzando Esplora soluzioni, aggiungere tre C++ classi al progetto denominate quanto segue.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="fc1e1-140">`CRenderer` (con distruttore virtuale)</span><span class="sxs-lookup"><span data-stu-id="fc1e1-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="fc1e1-141">Aprire Renderer. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="fc1e1-142">Aprire Renderer. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="fc1e1-143">Aprire RendererManager. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="fc1e1-144">Aprire RendererManager. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="fc1e1-145">Aprire TriangleRenderer. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="fc1e1-146">Aprire TriangleRenderer. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="fc1e1-147">Aprire stdafx. h nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="fc1e1-148">Aprire DllMain. cpp nell'editor di codice e sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="fc1e1-149">Aprire D3DContent. def nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="fc1e1-150">Sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-150">Replace the automatically generated code with the following code.</span></span>

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

12. <span data-ttu-id="fc1e1-151">Compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc1e1-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fc1e1-152">Next Steps</span></span>

- <span data-ttu-id="fc1e1-153">Ospitare il contenuto di Direct3D9 in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="fc1e1-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="fc1e1-154">Per ulteriori informazioni, vedere [procedura dettagliata: hosting di contenuto Direct3D9 in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="fc1e1-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc1e1-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc1e1-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="fc1e1-156">Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF</span><span class="sxs-lookup"><span data-stu-id="fc1e1-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="fc1e1-157">Procedura dettagliata: Hosting di contenuto Direct3D9 in WPF</span><span class="sxs-lookup"><span data-stu-id="fc1e1-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
