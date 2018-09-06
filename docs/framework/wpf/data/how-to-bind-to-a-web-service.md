---
title: "Procedura: eseguire l'associazione a un servizio Web"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 84c5aee8d2bc7d31ebcfee98930d9a0847c527d5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866553"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="bbe78-102">Procedura: eseguire l'associazione a un servizio Web</span><span class="sxs-lookup"><span data-stu-id="bbe78-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="bbe78-103">In questo esempio viene illustrato come eseguire l'associazione agli oggetti restituiti dalle chiamate al metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="bbe78-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe78-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbe78-104">Example</span></span>  
 <span data-ttu-id="bbe78-105">Questo esempio Usa la [servizio contenuto MSDN/TechNet Publishing System (MTPS)](https://go.microsoft.com/fwlink/?LinkId=95677) per recuperare l'elenco delle lingue supportate da un documento specificato.</span><span class="sxs-lookup"><span data-stu-id="bbe78-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="bbe78-106">Prima di chiamare un servizio Web, è necessario creare un riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="bbe78-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="bbe78-107">Per creare un riferimento Web al servizio MTPS usando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbe78-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="bbe78-108">Aprire il progetto in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbe78-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="bbe78-109">Dal **Project** menu, fare clic su **Aggiungi riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="bbe78-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="bbe78-110">Nella finestra di dialogo, impostare il **URL** al [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="bbe78-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="bbe78-111">Premere **andare** e quindi **aggiungere riferimento**.</span><span class="sxs-lookup"><span data-stu-id="bbe78-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="bbe78-112">Successivamente, si chiama il metodo del servizio Web e impostare il <xref:System.Windows.FrameworkElement.DataContext%2A> controllo appropriato o la finestra per l'oggetto restituito.</span><span class="sxs-lookup"><span data-stu-id="bbe78-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="bbe78-113">Il **GetContent** metodo del servizio MTPS accetta un riferimento per il **getContentRequest** oggetto.</span><span class="sxs-lookup"><span data-stu-id="bbe78-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="bbe78-114">Pertanto, l'esempio seguente imposta prima di tutto un oggetto della richiesta:</span><span class="sxs-lookup"><span data-stu-id="bbe78-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="bbe78-115">Dopo il <xref:System.Windows.FrameworkElement.DataContext%2A> è stato configurato, è possibile creare associazioni alle proprietà dell'oggetto che il <xref:System.Windows.FrameworkElement.DataContext%2A> è stata impostata su.</span><span class="sxs-lookup"><span data-stu-id="bbe78-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="bbe78-116">In questo esempio, il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato sul **getContentResponse** oggetto restituito dal **GetContent** (metodo).</span><span class="sxs-lookup"><span data-stu-id="bbe78-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="bbe78-117">Nell'esempio seguente, il <xref:System.Windows.Controls.ItemsControl> associa a e consente di visualizzare il **delle impostazioni locali** valori di **availableVersionsAndLocales** del **getContentResponse**.</span><span class="sxs-lookup"><span data-stu-id="bbe78-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="bbe78-118">Per informazioni sulla struttura dei **getContentResponse**, vedere [documentazione del servizio contenuto](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="bbe78-118">For information about the structure of **getContentResponse**, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe78-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe78-119">See Also</span></span>  
 [<span data-ttu-id="bbe78-120">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="bbe78-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="bbe78-121">Panoramica delle origini di associazione</span><span class="sxs-lookup"><span data-stu-id="bbe78-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="bbe78-122">Rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="bbe78-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
