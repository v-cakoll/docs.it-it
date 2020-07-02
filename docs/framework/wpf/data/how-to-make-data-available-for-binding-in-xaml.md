---
title: "Procedura: rendere i dati disponibili per l'associazione in XAML"
description: Scopri i vari modi in cui è possibile rendere disponibili i dati in base alle esigenze dell'applicazione in Windows Presentation Foundation (WPF).
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 16618ce8b19f5dd5854c4d126e7fc455f0428a28
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620794"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="171a7-103">Procedura: rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="171a7-103">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="171a7-104">In questo argomento vengono illustrati i vari modi in cui è possibile rendere disponibili i dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , a seconda delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="171a7-104">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="171a7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="171a7-105">Example</span></span>  
 <span data-ttu-id="171a7-106">Se si dispone di un oggetto Common Language Runtime (CLR) a cui si desidera eseguire [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] il binding, è possibile rendere disponibile l'oggetto per l'associazione in modo da definirlo come risorsa e assegnargli un `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="171a7-106">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="171a7-107">Nell'esempio seguente è presente un `Person` oggetto con una proprietà stringa denominata `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="171a7-107">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="171a7-108">L' `Person` oggetto (nella riga visualizzata evidenziata che contiene l' `<src>` elemento) viene definito nello spazio dei nomi denominato `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="171a7-108">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="171a7-109">È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , come illustrato nella riga evidenziata che contiene l' `<TextBlock>` elemento.</span><span class="sxs-lookup"><span data-stu-id="171a7-109">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="171a7-110">In alternativa, è possibile usare la <xref:System.Windows.Data.ObjectDataProvider> classe, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="171a7-110">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="171a7-111">L'associazione viene definita allo stesso modo, come illustrato nella riga evidenziata che contiene l' `<TextBlock>` elemento.</span><span class="sxs-lookup"><span data-stu-id="171a7-111">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="171a7-112">In questo particolare esempio, il risultato è lo stesso: è presente un oggetto <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe` .</span><span class="sxs-lookup"><span data-stu-id="171a7-112">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="171a7-113">Tuttavia, la <xref:System.Windows.Data.ObjectDataProvider> classe fornisce funzionalità come la possibilità di eseguire l'associazione al risultato di un metodo.</span><span class="sxs-lookup"><span data-stu-id="171a7-113">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="171a7-114">Se è necessaria la funzionalità fornita, è possibile scegliere di utilizzare la <xref:System.Windows.Data.ObjectDataProvider> classe.</span><span class="sxs-lookup"><span data-stu-id="171a7-114">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="171a7-115">Tuttavia, se si esegue il binding a un oggetto che è già stato creato, è necessario impostare `DataContext` nel codice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="171a7-115">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="171a7-116">Per accedere ai dati XML per l'associazione usando la <xref:System.Windows.Data.XmlDataProvider> classe, vedere eseguire l'associazione [a dati XML tramite un oggetto XmlDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="171a7-116">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="171a7-117">Per accedere ai dati XML per l'associazione usando la <xref:System.Windows.Data.ObjectDataProvider> classe, vedere [Bind to XDocument, XELEMENT o LINQ for XML query results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="171a7-117">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="171a7-118">Per informazioni su molti modi in cui è possibile specificare i dati a cui si sta associando, vedere [specificare l'origine del binding](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="171a7-118">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="171a7-119">Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti di Common Language Runtime (CLR) per l'associazione, vedere [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="171a7-119">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171a7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="171a7-120">See also</span></span>

- [<span data-ttu-id="171a7-121">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="171a7-121">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="171a7-122">Procedure</span><span class="sxs-lookup"><span data-stu-id="171a7-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
