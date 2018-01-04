---
title: 'Procedura: rendere i dati disponibili per l''associazione in XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c342f0d635a9220a88a2af79c76e2c1580dee2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="a157c-102">Procedura: rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="a157c-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="a157c-103">In questo argomento vengono illustrati i diversi modi, è possibile rendere disponibili dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a seconda delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a157c-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a157c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a157c-104">Example</span></span>  
 <span data-ttu-id="a157c-105">Se dispone di un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] oggetto che si desidera eseguire l'associazione da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], un modo è possibile renderlo disponibile per l'associazione per definirlo come una risorsa e assegnargli un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="a157c-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="a157c-106">In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="a157c-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="a157c-107">Il `Person` oggetto viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="a157c-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="a157c-108">È possibile associare all'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a157c-108">You can then bind to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as shown in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="a157c-109">In alternativa, è possibile utilizzare il <xref:System.Windows.Data.ObjectDataProvider> (classe), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a157c-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example.</span></span>  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 <span data-ttu-id="a157c-110">Definire l'associazione allo stesso modo:</span><span class="sxs-lookup"><span data-stu-id="a157c-110">You define the binding the same way:</span></span>  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <span data-ttu-id="a157c-111">In questo particolare esempio, il risultato è lo stesso: è un <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe`.</span><span class="sxs-lookup"><span data-stu-id="a157c-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="a157c-112">Tuttavia, la <xref:System.Windows.Data.ObjectDataProvider> classe fornisce funzionalità quali la possibilità di associare al risultato di un metodo.</span><span class="sxs-lookup"><span data-stu-id="a157c-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="a157c-113">È possibile scegliere di utilizzare la <xref:System.Windows.Data.ObjectDataProvider> classe se necessaria la funzionalità fornita.</span><span class="sxs-lookup"><span data-stu-id="a157c-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="a157c-114">Tuttavia, se si associa a un oggetto che è già stato creato, è necessario impostare il `DataContext` nel codice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a157c-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="a157c-115">Per accedere a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati per l'associazione mediante i <xref:System.Windows.Data.XmlDataProvider> classe, vedere [associazione a dati XML tramite un XMLDataProvider e query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a157c-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="a157c-116">Per accedere a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati per l'associazione mediante i <xref:System.Windows.Data.ObjectDataProvider> classe, vedere [associare XDocument, XElement o LINQ dei risultati della Query XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="a157c-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="a157c-117">Per informazioni sulle diverse modalità con cui è possibile specificare i dati che si desidera associare a, vedere [specificare l'origine di associazione](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="a157c-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="a157c-118">Per informazioni sui tipi di dati è possibile associare o come implementare la propria [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] degli oggetti per l'associazione, vedere [Cenni preliminari sulle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a157c-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a157c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a157c-119">See Also</span></span>  
 [<span data-ttu-id="a157c-120">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="a157c-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a157c-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a157c-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
