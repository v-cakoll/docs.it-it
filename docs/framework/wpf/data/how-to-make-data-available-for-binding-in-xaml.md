---
title: "Procedura: rendere i dati disponibili per l'associazione in XAML"
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174186"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="6f0ed-102">Procedura: rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="6f0ed-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="6f0ed-103">In questo argomento vengono illustrati i vari [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]modi in cui è possibile rendere i dati disponibili per l'associazione in , a seconda delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f0ed-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f0ed-104">Example</span></span>  
 <span data-ttu-id="6f0ed-105">Se si dispone di un oggetto Common Language Runtime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)](CLR) a cui si desidera eseguire l'associazione da , `x:Key`un modo per rendere l'oggetto disponibile per l'associazione consiste nel definirlo come risorsa e assegnargli un' estensione .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="6f0ed-106">Nell'esempio seguente si `Person` dispone di un `PersonName`oggetto con una proprietà stringa denominata .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="6f0ed-107">L'oggetto `Person` (nella riga evidenziata `<src>` che contiene l'elemento) è definito nello spazio dei nomi denominato `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="6f0ed-108">È quindi possibile <xref:System.Windows.Controls.TextBlock> associare il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]controllo all'oggetto in `<TextBlock>` , come illustrato nella riga evidenziata che contiene l'elemento .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="6f0ed-109">In alternativa, è <xref:System.Windows.Data.ObjectDataProvider> possibile utilizzare la classe, come nell'esempio seguente:Alternatively, you can use the class, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="6f0ed-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="6f0ed-110">L'associazione viene definita nello stesso modo, `<TextBlock>` come viene visualizzata la riga evidenziata che contiene l'elemento.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="6f0ed-111">In questo particolare esempio, il risultato <xref:System.Windows.Controls.TextBlock> è lo `Joe`stesso: si dispone di un con il contenuto di testo .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="6f0ed-112">Tuttavia, <xref:System.Windows.Data.ObjectDataProvider> la classe fornisce funzionalità, ad esempio la possibilità di associare al risultato di un metodo.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="6f0ed-113">È possibile scegliere <xref:System.Windows.Data.ObjectDataProvider> di utilizzare la classe se è necessaria la funzionalità che fornisce.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="6f0ed-114">Tuttavia, se si esegue l'associazione a un oggetto `DataContext` che è già stato creato, è necessario impostare il nel codice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="6f0ed-115">Per accedere ai dati <xref:System.Windows.Data.XmlDataProvider> XML per l'associazione mediante la classe, vedere [Associazione a dati XML tramite un XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6f0ed-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="6f0ed-116">Per accedere ai dati <xref:System.Windows.Data.ObjectDataProvider> XML per l'associazione tramite la classe, vedere [Associare a XDocument, XElement o LINQ per i risultati](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)delle query XML.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="6f0ed-117">Per informazioni sui molti modi in cui è possibile specificare i dati a cui si esegue l'associazione, vedere [Specificare l'origine dell'associazione](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="6f0ed-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="6f0ed-118">Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti CLR (Common Language Runtime) personalizzati per l'associazione, vedere [Cenni preliminari](binding-sources-overview.md)sulle origini di associazione .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0ed-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f0ed-119">See also</span></span>

- [<span data-ttu-id="6f0ed-120">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="6f0ed-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6f0ed-121">Argomenti relativi alle procedure</span><span class="sxs-lookup"><span data-stu-id="6f0ed-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
