---
title: 'Procedura: eseguire l''associazione ai risultati di una query XDocument, XElement o LINQ to XML'
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
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b39c45a7c85155a0fb46e8e176da5979e52e6e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="c9cd8-102">Procedura: eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c9cd8-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="c9cd8-103">In questo esempio viene illustrato come associare i dati XML da un <xref:System.Windows.Controls.ItemsControl> utilizzando <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9cd8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9cd8-104">Example</span></span>  
 <span data-ttu-id="c9cd8-105">Il codice XAML seguente definisce un <xref:System.Windows.Controls.ItemsControl> e include un modello di dati di tipo `Planet` nel `http://planetsNS` spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="c9cd8-106">Un tipo di dati XML che occupa uno spazio dei nomi deve includere lo spazio dei nomi tra parentesi graffe e, se viene visualizzato dove viene visualizzata un'estensione di markup XAML, deve precedere lo spazio dei nomi con una sequenza di escape in parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="c9cd8-107">Questo codice associa a proprietà dinamiche che corrispondono al <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> metodi di <xref:System.Xml.Linq.XElement> classe.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="c9cd8-108">Le proprietà dinamiche consentono al codice XAML di eseguire un'associazione a proprietà dinamiche che condividono i nomi dei metodi.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="c9cd8-109">Per altre informazioni, vedere [Proprietà dinamiche di LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties).</span><span class="sxs-lookup"><span data-stu-id="c9cd8-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="c9cd8-110">Si noti che la dichiarazione predefinita dello spazio dei nomi per il codice XML non viene applicata ai nomi di attributo.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="c9cd8-111">L'esempio di codice c# chiama <xref:System.Xml.Linq.XDocument.Load%2A> e imposta il contesto di dati del pannello stack su tutti i sottoelementi dell'elemento denominato `SolarSystemPlanets` nel `http://planetsNS` spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="c9cd8-112">Dati XML possono essere archiviati come risorsa XAML mediante <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="c9cd8-113">Per un esempio completo, vedere [Codice sorgente di L2DBForm.xaml](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span><span class="sxs-lookup"><span data-stu-id="c9cd8-113">For a complete example, see  [L2DBForm.xaml Source Code](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span></span> <span data-ttu-id="c9cd8-114">L'esempio seguente illustra come il codice può impostare il contesto dei dati per una risorsa oggetto.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="c9cd8-115">Le proprietà dinamiche che eseguono il mapping a <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> flessibilità all'interno di XAML.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="c9cd8-116">Il codice può anche eseguire l'associazione ai risultati di una query LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="c9cd8-117">Questo esempio esegue l'associazione ai risultati di una query ordinati in base al valore di un elemento.</span><span class="sxs-lookup"><span data-stu-id="c9cd8-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="c9cd8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9cd8-118">See Also</span></span>  
 [<span data-ttu-id="c9cd8-119">Panoramica delle origini di associazione</span><span class="sxs-lookup"><span data-stu-id="c9cd8-119">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="c9cd8-120">Panoramica dei data binding WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c9cd8-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [<span data-ttu-id="c9cd8-121">Esempio di data binding WPF tramite LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c9cd8-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [<span data-ttu-id="c9cd8-122">Proprietà dinamiche in LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="c9cd8-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
