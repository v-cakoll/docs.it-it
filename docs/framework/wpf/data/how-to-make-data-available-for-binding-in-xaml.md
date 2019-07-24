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
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401500"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="f8b2a-102">Procedura: Rendere i dati disponibili per il binding in XAML</span><span class="sxs-lookup"><span data-stu-id="f8b2a-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="f8b2a-103">In questo argomento vengono illustrati i vari modi in cui è possibile [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]rendere disponibili i dati per l'associazione in, a seconda delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b2a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8b2a-104">Example</span></span>  
 <span data-ttu-id="f8b2a-105">Se si dispone di un oggetto Common Language Runtime (CLR) a cui si [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]desidera eseguire il binding, è possibile rendere disponibile l'oggetto per l'associazione in modo da definirlo come risorsa e assegnargli un. `x:Key`</span><span class="sxs-lookup"><span data-stu-id="f8b2a-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="f8b2a-106">Nell'esempio seguente è presente un `Person` oggetto con una proprietà stringa denominata. `PersonName`</span><span class="sxs-lookup"><span data-stu-id="f8b2a-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f8b2a-107">L' `Person` oggetto (nella riga visualizzata evidenziata che contiene l' `<src>` elemento) viene definito nello spazio dei nomi `SDKSample`denominato.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="f8b2a-108">È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come illustrato nella riga evidenziata che contiene `<TextBlock>` l'elemento.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="f8b2a-109">In alternativa, è possibile usare la <xref:System.Windows.Data.ObjectDataProvider> classe, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f8b2a-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="f8b2a-110">L'associazione viene definita allo stesso modo, come illustrato nella riga evidenziata che `<TextBlock>` contiene l'elemento.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="f8b2a-111">In questo particolare esempio, il risultato è lo stesso: è presente un <xref:System.Windows.Controls.TextBlock> oggetto con il contenuto `Joe`di testo.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="f8b2a-112">Tuttavia, la <xref:System.Windows.Data.ObjectDataProvider> classe fornisce funzionalità come la possibilità di eseguire l'associazione al risultato di un metodo.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="f8b2a-113">Se è necessaria la funzionalità fornita <xref:System.Windows.Data.ObjectDataProvider> , è possibile scegliere di utilizzare la classe.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="f8b2a-114">Tuttavia, se si esegue il `DataContext` binding a un oggetto che è già stato creato, è necessario impostare nel codice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f8b2a-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="f8b2a-115">Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati per l'associazione <xref:System.Windows.Data.XmlDataProvider> usando la classe, vedere eseguire l'associazione [a dati XML tramite un oggetto XmlDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f8b2a-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="f8b2a-116">Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati per l'associazione <xref:System.Windows.Data.ObjectDataProvider> usando la classe, vedere [Bind to XDocument, XElement o LINQ for XML query results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="f8b2a-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="f8b2a-117">Per informazioni su molti modi in cui è possibile specificare i dati a cui si sta associando, vedere [specificare l'origine del binding](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="f8b2a-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="f8b2a-118">Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti di Common Language Runtime (CLR) per l'associazione, vedere [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f8b2a-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b2a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8b2a-119">See also</span></span>

- [<span data-ttu-id="f8b2a-120">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="f8b2a-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="f8b2a-121">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f8b2a-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
