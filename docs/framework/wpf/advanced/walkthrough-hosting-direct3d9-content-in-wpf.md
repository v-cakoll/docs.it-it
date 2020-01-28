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
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="284f8-102">Procedura dettagliata: hosting di contenuto Direct3D9 in WPF</span><span class="sxs-lookup"><span data-stu-id="284f8-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>

<span data-ttu-id="284f8-103">In questa procedura dettagliata viene illustrato come ospitare il contenuto di Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="284f8-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="284f8-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="284f8-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="284f8-105">Creare un progetto WPF per ospitare il contenuto di Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="284f8-105">Create a WPF project to host the Direct3D9 content.</span></span>

- <span data-ttu-id="284f8-106">Importa il contenuto di Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="284f8-106">Import the Direct3D9 content.</span></span>

- <span data-ttu-id="284f8-107">Visualizzare il contenuto Direct3D9 usando la classe <xref:System.Windows.Interop.D3DImage>.</span><span class="sxs-lookup"><span data-stu-id="284f8-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>

 <span data-ttu-id="284f8-108">Al termine, si saprà come ospitare il contenuto di Direct3D9 in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="284f8-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="284f8-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="284f8-109">Prerequisites</span></span>

<span data-ttu-id="284f8-110">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="284f8-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="284f8-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="284f8-111">Visual Studio.</span></span>

- <span data-ttu-id="284f8-112">DirectX SDK 9 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="284f8-112">DirectX SDK 9 or later.</span></span>

- <span data-ttu-id="284f8-113">Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF.</span><span class="sxs-lookup"><span data-stu-id="284f8-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="284f8-114">Per altre informazioni, vedere [interoperatività di WPF e Direct3D9](wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: creazione di contenuto Direct3D9 per l'hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="284f8-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>

## <a name="creating-the-wpf-project"></a><span data-ttu-id="284f8-115">Creazione del progetto WPF</span><span class="sxs-lookup"><span data-stu-id="284f8-115">Creating the WPF Project</span></span>

<span data-ttu-id="284f8-116">Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="284f8-116">The first step is to create the project for the WPF application.</span></span>

### <a name="to-create-the-wpf-project"></a><span data-ttu-id="284f8-117">Per creare il progetto WPF</span><span class="sxs-lookup"><span data-stu-id="284f8-117">To create the WPF project</span></span>

<span data-ttu-id="284f8-118">Creare un nuovo progetto di applicazione WPF in C# un oggetto visivo denominato `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="284f8-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="284f8-119">Per altre informazioni, vedere [Procedura dettagliata: La prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="284f8-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

<span data-ttu-id="284f8-120">MainWindow. XAML viene aperto in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="284f8-120">MainWindow.xaml opens in the WPF Designer.</span></span>

## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="284f8-121">Importazione del contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="284f8-121">Importing the Direct3D9 Content</span></span>

<span data-ttu-id="284f8-122">Il contenuto Direct3D9 viene importato da una DLL non gestita usando l'attributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="284f8-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>

### <a name="to-import-direct3d9-content"></a><span data-ttu-id="284f8-123">Per importare il contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="284f8-123">To import Direct3D9 content</span></span>

1. <span data-ttu-id="284f8-124">Aprire MainWindow.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="284f8-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>

2. <span data-ttu-id="284f8-125">Sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="284f8-125">Replace the automatically generated code with the following code.</span></span>

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="284f8-126">Hosting del contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="284f8-126">Hosting the Direct3D9 Content</span></span>

<span data-ttu-id="284f8-127">Infine, usare la classe <xref:System.Windows.Interop.D3DImage> per ospitare il contenuto di Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="284f8-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>

### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="284f8-128">Per ospitare il contenuto di Direct3D9</span><span class="sxs-lookup"><span data-stu-id="284f8-128">To host the Direct3D9 content</span></span>

1. <span data-ttu-id="284f8-129">In MainWindow. xaml sostituire il codice XAML generato automaticamente con il codice XAML seguente.</span><span class="sxs-lookup"><span data-stu-id="284f8-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. <span data-ttu-id="284f8-130">Compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="284f8-130">Build the project.</span></span>

3. <span data-ttu-id="284f8-131">Copiare la DLL che contiene il contenuto di Direct3D9 nella cartella bin/debug.</span><span class="sxs-lookup"><span data-stu-id="284f8-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>

4. <span data-ttu-id="284f8-132">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="284f8-132">Press F5 to run the project.</span></span>

    <span data-ttu-id="284f8-133">Il contenuto di Direct3D9 viene visualizzato all'interno dell'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="284f8-133">The Direct3D9 content appears within the WPF application.</span></span>

## <a name="see-also"></a><span data-ttu-id="284f8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="284f8-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="284f8-135">Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF</span><span class="sxs-lookup"><span data-stu-id="284f8-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
