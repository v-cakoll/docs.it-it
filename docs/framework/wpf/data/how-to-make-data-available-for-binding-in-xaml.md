---
title: 'Procedura: Rendere i dati disponibili per il binding in XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2d51f06da31482c46b04d1eb86172c3eda246c20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145366"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="643e3-102">Procedura: Rendere i dati disponibili per il binding in XAML</span><span class="sxs-lookup"><span data-stu-id="643e3-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="643e3-103">In questo argomento illustra vari modi in cui è possibile rendere disponibili dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a seconda delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="643e3-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="643e3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="643e3-104">Example</span></span>  
 <span data-ttu-id="643e3-105">Se si dispone di un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] si vuole eseguire l'associazione da dell'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], un modo è possibile rendere disponibile l'oggetto per l'associazione per definirlo come una risorsa e assegnargli un `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="643e3-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="643e3-106">Nell'esempio seguente, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="643e3-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="643e3-107">Il `Person` oggetti (nella riga evidenziata che contiene il `<src>` elemento) viene definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="643e3-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="643e3-108">È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come evidenziato la riga che contiene il `<TextBlock>` Mostra elemento.</span><span class="sxs-lookup"><span data-stu-id="643e3-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="643e3-109">In alternativa, è possibile usare il <xref:System.Windows.Data.ObjectDataProvider> (classe), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="643e3-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="643e3-110">Definire l'associazione nello stesso modo, la riga evidenziata che contiene il `<TextBlock>` Mostra elemento.</span><span class="sxs-lookup"><span data-stu-id="643e3-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="643e3-111">In questo particolare esempio, il risultato è lo stesso: è necessario un <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe`.</span><span class="sxs-lookup"><span data-stu-id="643e3-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="643e3-112">Tuttavia, il <xref:System.Windows.Data.ObjectDataProvider> classe offre funzionalità quali la possibilità di associare al risultato di un metodo.</span><span class="sxs-lookup"><span data-stu-id="643e3-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="643e3-113">È possibile scegliere di usare il <xref:System.Windows.Data.ObjectDataProvider> classe se necessaria la funzionalità fornita.</span><span class="sxs-lookup"><span data-stu-id="643e3-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="643e3-114">Tuttavia, se esegue il binding a un oggetto che è già stato creato, è necessario impostare il `DataContext` nel codice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="643e3-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="643e3-115">Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati per l'associazione mediante il <xref:System.Windows.Data.XmlDataProvider> classe, vedere [eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="643e3-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="643e3-116">Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati per l'associazione mediante il <xref:System.Windows.Data.ObjectDataProvider> classe, vedere [eseguire l'associazione a XDocument, XElement o LINQ for dei risultati di Query XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="643e3-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="643e3-117">Per informazioni su molti aspetti è possibile specificare i dati a cui si esegue l'associazione, vedere [specificare l'origine del Binding](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="643e3-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="643e3-118">Per informazioni su quali tipi di dati è possibile associare a o come implementare il proprio [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] degli oggetti per l'associazione, vedere [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="643e3-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643e3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="643e3-119">See also</span></span>

- [<span data-ttu-id="643e3-120">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="643e3-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="643e3-121">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="643e3-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
