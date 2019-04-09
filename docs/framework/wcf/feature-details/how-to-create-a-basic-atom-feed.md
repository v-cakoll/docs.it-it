---
title: 'Procedura: Creare un feed atom di base'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
ms.openlocfilehash: 2d254d0c87bb9e0a2ce10b8cba0233680b24f4be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181558"
---
# <a name="how-to-create-a-basic-atom-feed"></a><span data-ttu-id="01bd6-102">Procedura: Creare un feed atom di base</span><span class="sxs-lookup"><span data-stu-id="01bd6-102">How to: Create a Basic Atom Feed</span></span>
<span data-ttu-id="01bd6-103">Windows Communication Foundation (WCF) consente di creare un servizio che espone un feed di diffusione.</span><span class="sxs-lookup"><span data-stu-id="01bd6-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="01bd6-104">In questo argomento viene illustrato come creare un servizio di diffusione che espone un feed di diffusione Atom.</span><span class="sxs-lookup"><span data-stu-id="01bd6-104">This topic discusses how to create a syndication service that exposes an Atom syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="01bd6-105">Per creare un servizio di diffusione di base</span><span class="sxs-lookup"><span data-stu-id="01bd6-105">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="01bd6-106">Definire un contratto di servizio usando un'interfaccia contrassegnata con l'attributo <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01bd6-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="01bd6-107">Ogni operazione esposta come feed di diffusione deve restituire un oggetto <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="01bd6-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> object.</span></span>  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="01bd6-108">Tutte le operazioni del servizio che applicano <xref:System.ServiceModel.Web.WebGetAttribute> vengono mappate alle richieste HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="01bd6-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> are mapped to HTTP GET requests.</span></span> <span data-ttu-id="01bd6-109">Per eseguire il mapping dell'operazione a un metodo HTTP diverso, utilizzare invece <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01bd6-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="01bd6-110">Per altre informazioni, vedere [Procedura: Creare un servizio HTTP Web WCF](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="01bd6-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2.  <span data-ttu-id="01bd6-111">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="01bd6-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3.  <span data-ttu-id="01bd6-112">Creare un oggetto <xref:System.ServiceModel.Syndication.SyndicationFeed> e aggiungere un autore, una categoria e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="01bd6-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4.  <span data-ttu-id="01bd6-113">Creare diversi oggetti <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="01bd6-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5.  <span data-ttu-id="01bd6-114">Aggiungere gli oggetti <xref:System.ServiceModel.Syndication.SyndicationItem> al feed.</span><span class="sxs-lookup"><span data-stu-id="01bd6-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> objects to the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6.  <span data-ttu-id="01bd6-115">Restituire il feed.</span><span class="sxs-lookup"><span data-stu-id="01bd6-115">Return the feed.</span></span>  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="01bd6-116">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="01bd6-116">To host the service</span></span>  
  
1.  <span data-ttu-id="01bd6-117">Creare un oggetto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="01bd6-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2.  <span data-ttu-id="01bd6-118">Aprire l'host del servizio, caricare il feed dal servizio, visualizzare il feed e aspettare che l'utente prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="01bd6-118">Open the service host, load the feed from the service, display the feed, and wait for the user to press ENTER.</span></span>  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="01bd6-119">Per chiamare GetBlog() con un HTTP GET</span><span class="sxs-lookup"><span data-stu-id="01bd6-119">To call GetBlog() with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="01bd6-120">Aprire Internet Explorer, digitare l'URL seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="01bd6-120">Open Internet Explorer, type the following URL, and press ENTER:</span></span> `http://localhost:8000/BlogService/GetBlog`  
  
     <span data-ttu-id="01bd6-121">L'URL contiene l'indirizzo di base del servizio (`http://localhost:8000/BlogService`), l'indirizzo relativo dell'endpoint e l'operazione di servizio da chiamare.</span><span class="sxs-lookup"><span data-stu-id="01bd6-121">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="01bd6-122">Per chiamare GetBlog() dal codice</span><span class="sxs-lookup"><span data-stu-id="01bd6-122">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="01bd6-123">Creare un <xref:System.Xml.XmlReader> con l'indirizzo di base e il metodo che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="01bd6-123">Create a <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="01bd6-124">Chiamare il metodo statico <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> passando l'oggetto <xref:System.Xml.XmlReader> appena creato.</span><span class="sxs-lookup"><span data-stu-id="01bd6-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="01bd6-125">Verrà in tal modo richiamata l'operazione del servizio e verrà popolato un nuovo <xref:System.ServiceModel.Syndication.SyndicationFeed> con il formattatore restituito dall'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="01bd6-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="01bd6-126">Accedere all'oggetto feed.</span><span class="sxs-lookup"><span data-stu-id="01bd6-126">Access the feed object.</span></span>  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="01bd6-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="01bd6-127">Example</span></span>  
 <span data-ttu-id="01bd6-128">Di seguito è riportato il codice completo per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="01bd6-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01bd6-129">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="01bd6-129">Compiling the Code</span></span>  
 <span data-ttu-id="01bd6-130">Durante la compilazione del codice precedente, fare riferimento a System.ServiceModel.dll e a System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="01bd6-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bd6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01bd6-131">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
