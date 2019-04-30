---
title: Esempio di tecnologia per la serializzazione di generics dei servizi Web
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 6549dc1c3d428a5fb74fe0212549ef3f3f6510d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018047"
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="87eff-102">Esempio di tecnologia per la serializzazione di generics dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="87eff-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="87eff-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="87eff-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="87eff-104">In questo esempio viene illustrato come utilizzare e controllare la serializzazione di generics nei servizi Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="87eff-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="87eff-105">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87eff-105">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="87eff-106">Aprire Visual Studio e scegliere **Nuovo sito Web** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="87eff-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2. <span data-ttu-id="87eff-107">Nel riquadro sinistro della finestra di dialogo **Nuovo sito Web** scegliere il linguaggio di programmazione desiderato e quindi nel riquadro destro selezionare **Servizio Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="87eff-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3. <span data-ttu-id="87eff-108">Fare clic su **Sfoglia** e passare alla sottodirectory \CS\GenericsService.</span><span class="sxs-lookup"><span data-stu-id="87eff-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4. <span data-ttu-id="87eff-109">Selezionare il file Service.asmx per aprirlo in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="87eff-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5. <span data-ttu-id="87eff-110">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="87eff-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87eff-111">I primi cinque passaggi di questo elenco sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="87eff-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="87eff-112">Il runtime di .NET Framework genererà automaticamente il servizio Web la prima volta che verrà richiesto.</span><span class="sxs-lookup"><span data-stu-id="87eff-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87eff-113">Di seguito sono indicati i passaggi necessari per compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87eff-113">The following steps are required to build the sample.</span></span>  
  
1. <span data-ttu-id="87eff-114">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi nella sottodirectory \CS.</span><span class="sxs-lookup"><span data-stu-id="87eff-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the \CS subdirectory.</span></span>  
  
2. <span data-ttu-id="87eff-115">Fare clic con il pulsante destro del mouse sull'icona della sottodirectory GenericsService e quindi scegliere **Condivisione e sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="87eff-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3. <span data-ttu-id="87eff-116">Nella scheda **Condivisione Web** selezionare **Condividi questa cartella**.</span><span class="sxs-lookup"><span data-stu-id="87eff-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="87eff-117">Prendere nota del nome della directory virtuale indicato nel riquadro **Alias** in quanto servirà per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87eff-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="87eff-118">Per compilare l'esempio utilizzando Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="87eff-118">To build the sample using Internet Information Services</span></span>  
  
1. <span data-ttu-id="87eff-119">Aprire lo snap-in di gestione **Internet Information Services** ed espandere **Siti Web**.</span><span class="sxs-lookup"><span data-stu-id="87eff-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2. <span data-ttu-id="87eff-120">Fare clic su **Sito Web predefinito**, selezionare **Nuovo** e quindi selezionare **Directory virtuale** per avviare la **Creazione guidata Directory virtuale**.</span><span class="sxs-lookup"><span data-stu-id="87eff-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3. <span data-ttu-id="87eff-121">Fare clic su **Avanti**, immettere l'alias pubblico per la directory virtuale e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="87eff-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4. <span data-ttu-id="87eff-122">Immettere il percorso della directory in cui è stato salvato l'esempio (generalmente la sottodirectory \CS\GenericsService) e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="87eff-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="87eff-123">Fare clic su **Avanti** per terminare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="87eff-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="87eff-124">Prendere nota del nome della directory virtuale indicato nel riquadro **Alias** in quanto servirà per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87eff-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="87eff-125">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="87eff-125">To run the sample</span></span>  
  
1. <span data-ttu-id="87eff-126">Aprire una finestra del browser, quindi fare clic sulla barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="87eff-126">Open a browser window and select its address bar.</span></span>  
  
2. <span data-ttu-id="87eff-127">Tipo di `http://localhost/[virtual directory]/Service.asmx`, dove `[virtual directory]` rappresenta la directory virtuale creata durante la compilazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="87eff-127">Type `http://localhost/[virtual directory]/Service.asmx`, where `[virtual directory]` represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87eff-128">Note</span><span class="sxs-lookup"><span data-stu-id="87eff-128">Remarks</span></span>  
 <span data-ttu-id="87eff-129">Nell'esempio viene visualizzata una pagina ASP.NET predefinita che contiene collegamenti alla definizione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="87eff-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="87eff-130">Oltre a modificare il codice sorgente per il servizio Web, è possibile personalizzare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="87eff-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="87eff-131">Per altre informazioni, vedere [Compilazione di client dei servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="87eff-131">For more information, see [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87eff-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87eff-132">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="87eff-133">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="87eff-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- <span data-ttu-id="87eff-134">[Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="87eff-134">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
