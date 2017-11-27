---
title: 'Procedura dettagliata: hosting di contenuto Direct3D9 in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec80eed37777fc7b17b435e1bef63ecbb94bdf46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="11997-102">Procedura dettagliata: hosting di contenuto Direct3D9 in WPF</span><span class="sxs-lookup"><span data-stu-id="11997-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="11997-103">Questa procedura dettagliata viene illustrato come ospitare contenuto Direct3D9 in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="11997-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="11997-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="11997-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="11997-105">Creare un progetto WPF per ospitare il contenuto Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="11997-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="11997-106">Importare il contenuto Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="11997-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="11997-107">Visualizzare il contenuto Direct3D9 utilizzando la <xref:System.Windows.Interop.D3DImage> classe.</span><span class="sxs-lookup"><span data-stu-id="11997-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="11997-108">Al termine, si saprà come ospitare contenuto Direct3D9 in un'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="11997-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11997-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="11997-109">Prerequisites</span></span>  
 <span data-ttu-id="11997-110">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="11997-110">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="11997-111">.</span><span class="sxs-lookup"><span data-stu-id="11997-111">.</span></span>  
  
-   <span data-ttu-id="11997-112">DirectX SDK 9 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="11997-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="11997-113">Una DLL che contiene contenuto Direct3D9 in un formato compatibile con WPF.</span><span class="sxs-lookup"><span data-stu-id="11997-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="11997-114">Per ulteriori informazioni, vedere [interoperatività di WPF e Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) e [procedura dettagliata: creazione di contenuto Direct3D9 per l'Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="11997-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="11997-115">Creazione del progetto WPF</span><span class="sxs-lookup"><span data-stu-id="11997-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="11997-116">Il primo passaggio consiste nel creare il progetto per l'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="11997-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="11997-117">Per creare il progetto WPF</span><span class="sxs-lookup"><span data-stu-id="11997-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="11997-118">Creare un nuovo progetto di applicazione WPF in Visual c# denominato `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="11997-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="11997-119">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="11997-119">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="11997-120">MainWindow. XAML viene aperto nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11997-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="11997-121">L'importazione del contenuto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="11997-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="11997-122">Per importare il contenuto di Direct3D9 da una DLL non gestita usando il `DllImport` attributo.</span><span class="sxs-lookup"><span data-stu-id="11997-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="11997-123">Per importare il contenuto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="11997-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="11997-124">Aprire MainWindow.xaml.cs nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="11997-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="11997-125">Sostituire il codice generato automaticamente con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="11997-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="11997-126">Ospitare il contenuto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="11997-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="11997-127">Infine, utilizzare la <xref:System.Windows.Interop.D3DImage> classe per ospitare il contenuto Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="11997-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="11997-128">Per ospitare il contenuto Direct3D9</span><span class="sxs-lookup"><span data-stu-id="11997-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="11997-129">In MainWindow. XAML, sostituire il codice XAML generato automaticamente con il seguente codice XAML.</span><span class="sxs-lookup"><span data-stu-id="11997-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="11997-130">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="11997-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="11997-131">Copiare la DLL che contiene il contenuto Direct3D9 nella cartella bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="11997-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="11997-132">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="11997-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="11997-133">Il contenuto Direct3D9 viene visualizzato all'interno dell'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="11997-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11997-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11997-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="11997-135">Considerazioni sulle prestazioni per l'interoperabilità fra Direct3D9 e WPF</span><span class="sxs-lookup"><span data-stu-id="11997-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
