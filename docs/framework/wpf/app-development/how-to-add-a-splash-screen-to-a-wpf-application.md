---
title: "Procedura: aggiungere una schermata iniziale in un'applicazione WPF"
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 06d6cb7c5a5081d3b6c4979ab50e1caaa726acbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547001"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="d6681-102">Procedura: aggiungere una schermata iniziale in un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="d6681-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="d6681-103">In questo argomento viene illustrato come aggiungere una finestra di avvio, o *schermata*, a un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d6681-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="d6681-104">Per aggiungere un'immagine esistente come schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="d6681-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="d6681-105">Creare o trovare un'immagine che si desidera utilizzare per la schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="d6681-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="d6681-106">È possibile utilizzare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="d6681-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="d6681-107">Ad esempio, è possibile utilizzare il formato TIFF, GIF, JPEG, PNG o BMP.</span><span class="sxs-lookup"><span data-stu-id="d6681-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="d6681-108">Aggiungere il file di immagine al progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="d6681-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="d6681-109">Per ulteriori informazioni, vedere [NIB: procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="d6681-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="d6681-110">In Esplora soluzioni, selezionare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="d6681-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="d6681-111">Nella finestra Proprietà fare clic sulla freccia giù per la **azione di compilazione** proprietà.</span><span class="sxs-lookup"><span data-stu-id="d6681-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="d6681-112">Selezionare **SplashScreen** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d6681-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6681-113">Se non viene visualizzato il **SplashScreen** opzione, assicurarsi di controllare che si stia usando [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d6681-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="d6681-114">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6681-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="d6681-115">L'immagine della schermata iniziale viene visualizzato al centro dello schermo e quindi scompare quando viene visualizzata la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6681-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="d6681-116">Per rimuovere la schermata da un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d6681-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="d6681-117">In Esplora soluzioni, selezionare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="d6681-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="d6681-118">Nella finestra Proprietà impostare il **azione di compilazione** a **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="d6681-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="d6681-119">Per rimuovere la schermata da un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d6681-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="d6681-120">In Esplora soluzioni, eliminare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="d6681-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="d6681-121">Escludere l'immagine della schermata iniziale dal progetto.</span><span class="sxs-lookup"><span data-stu-id="d6681-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6681-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6681-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="d6681-123">NIB: procedura: aggiungere elementi esistenti a un progetto</span><span class="sxs-lookup"><span data-stu-id="d6681-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
