---
title: "Procedura: Utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: bd2a156920057dc197fabbaa46e3a2d886a1b322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600349"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="954aa-102">Procedura: Utilizzare gli spazi dei nomi XML nell'associazione dati</span><span class="sxs-lookup"><span data-stu-id="954aa-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="954aa-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="954aa-103">Example</span></span>  
 <span data-ttu-id="954aa-104">Questo esempio spiega come gestire gli spazi dei nomi specificati nell'origine del binding [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="954aa-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="954aa-105">Se i dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] presentano la definizione dello spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="954aa-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="954aa-106">È possibile usare la <xref:System.Windows.Data.XmlNamespaceMapping> elemento per mappare lo spazio dei nomi per un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="954aa-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="954aa-107">È quindi possibile usare la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento al [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="954aa-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="954aa-108">Il <xref:System.Windows.Controls.ListBox> in questo esempio consente di visualizzare il *title* e *elementi* della ognuno *elemento*.</span><span class="sxs-lookup"><span data-stu-id="954aa-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="954aa-109">Si noti che il <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> si specifica non deve corrispondere a quello usato nel [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] origine; se il prefisso viene modificato nel [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] origine il mapping rimarrà valido.</span><span class="sxs-lookup"><span data-stu-id="954aa-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="954aa-110">In questo particolare esempio, il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati provengono da un servizio web, ma la <xref:System.Windows.Data.XmlNamespaceMapping> elemento funziona anche con inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati in un file incorporato.</span><span class="sxs-lookup"><span data-stu-id="954aa-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954aa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="954aa-111">See also</span></span>
- [<span data-ttu-id="954aa-112">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="954aa-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="954aa-113">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="954aa-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="954aa-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="954aa-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
