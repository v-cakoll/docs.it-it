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
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449972"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="2efe7-102">Procedura: eseguire l'associazione a un servizio Web</span><span class="sxs-lookup"><span data-stu-id="2efe7-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="2efe7-103">In questo esempio viene illustrato come eseguire l'associazione a oggetti restituiti dalle chiamate al metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="2efe7-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2efe7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2efe7-104">Example</span></span>  
 <span data-ttu-id="2efe7-105">In questo esempio viene utilizzato il servizio contenuto MTPS (MSDN/TechNet Publishing System) per recuperare l'elenco delle lingue supportate da un documento specificato.</span><span class="sxs-lookup"><span data-stu-id="2efe7-105">This example uses the MSDN/TechNet Publishing System (MTPS) Content Service to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="2efe7-106">Prima di chiamare un servizio Web, è necessario crearvi un riferimento.</span><span class="sxs-lookup"><span data-stu-id="2efe7-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="2efe7-107">Per creare un riferimento Web al servizio MTPS con Visual Studio, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2efe7-107">To create a Web reference to the MTPS service using Visual Studio, follow the following steps:</span></span>  
  
1. <span data-ttu-id="2efe7-108">Apri il progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2efe7-108">Open your project in Visual Studio.</span></span>  
  
2. <span data-ttu-id="2efe7-109">Scegliere **Aggiungi riferimento Web**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="2efe7-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3. <span data-ttu-id="2efe7-110">Nella finestra di dialogo impostare l' **URL** su [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span><span class="sxs-lookup"><span data-stu-id="2efe7-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4. <span data-ttu-id="2efe7-111">Premere **go** e quindi **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="2efe7-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="2efe7-112">Chiamare quindi il metodo del servizio Web e impostare l'<xref:System.Windows.FrameworkElement.DataContext%2A> del controllo o della finestra appropriata sull'oggetto restituito.</span><span class="sxs-lookup"><span data-stu-id="2efe7-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="2efe7-113">Il `GetContent` metodo del servizio MTPS accetta un riferimento all'oggetto `getContentRequest`.</span><span class="sxs-lookup"><span data-stu-id="2efe7-113">The `GetContent` method of the MTPS service takes a reference to the `getContentRequest` object.</span></span> <span data-ttu-id="2efe7-114">Di conseguenza, l'esempio seguente configura prima di tutto un oggetto Request:</span><span class="sxs-lookup"><span data-stu-id="2efe7-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="2efe7-115">Una volta impostato il <xref:System.Windows.FrameworkElement.DataContext%2A>, è possibile creare binding per le proprietà dell'oggetto su cui è stato impostato il <xref:System.Windows.FrameworkElement.DataContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2efe7-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="2efe7-116">In questo esempio, il <xref:System.Windows.FrameworkElement.DataContext%2A> viene impostato sull'oggetto `getContentResponse` restituito dal metodo `GetContent`.</span><span class="sxs-lookup"><span data-stu-id="2efe7-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the `getContentResponse` object returned by the `GetContent` method.</span></span> <span data-ttu-id="2efe7-117">Nell'esempio seguente, il <xref:System.Windows.Controls.ItemsControl> viene associato a e Visualizza i valori di `locale` di `availableVersionsAndLocales` di `getContentResponse`.</span><span class="sxs-lookup"><span data-stu-id="2efe7-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the `locale` values of `availableVersionsAndLocales` of `getContentResponse`.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="2efe7-118">Per informazioni sulla struttura di `getContentResponse`, vedere la [documentazione del servizio contenuto](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span><span class="sxs-lookup"><span data-stu-id="2efe7-118">For information about the structure of `getContentResponse`, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efe7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2efe7-119">See also</span></span>

- [<span data-ttu-id="2efe7-120">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="2efe7-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="2efe7-121">Panoramica delle origini di associazione</span><span class="sxs-lookup"><span data-stu-id="2efe7-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="2efe7-122">Rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="2efe7-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
