---
title: "Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 9d8ddc5445bac28c68cd6cc99acf3313613a8c7f
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919659"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="b3168-102">Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati</span><span class="sxs-lookup"><span data-stu-id="b3168-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="b3168-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3168-103">Example</span></span>
 <span data-ttu-id="b3168-104">Questo esempio spiega come gestire gli spazi dei nomi specificati nell'origine del binding [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3168-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>

 <span data-ttu-id="b3168-105">Se i dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] presentano la definizione dello spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="b3168-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="b3168-106">È possibile usare l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> per eseguire il mapping dello spazio dei nomi a una <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b3168-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="b3168-107">È quindi possibile usare il <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3168-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="b3168-108">Il <xref:System.Windows.Controls.ListBox> in questo esempio Visualizza il *titolo* e il controller di dominio *: data* di ogni *elemento*.</span><span class="sxs-lookup"><span data-stu-id="b3168-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="b3168-109">Si noti che la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificata non deve corrispondere a quella utilizzata nell'origine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; Se il prefisso viene modificato nell'origine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] il mapping continua a funzionare.</span><span class="sxs-lookup"><span data-stu-id="b3168-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>

 <span data-ttu-id="b3168-110">In questo particolare esempio, i dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] provengono da un servizio Web, ma l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> funziona anche con dati inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] in un file incorporato.</span><span class="sxs-lookup"><span data-stu-id="b3168-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3168-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3168-111">See also</span></span>

- [<span data-ttu-id="b3168-112">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="b3168-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="b3168-113">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b3168-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="b3168-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b3168-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
