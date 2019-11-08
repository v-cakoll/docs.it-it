---
title: "Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740582"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="4069e-102">Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati</span><span class="sxs-lookup"><span data-stu-id="4069e-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="4069e-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="4069e-103">Example</span></span>
 <span data-ttu-id="4069e-104">In questo esempio viene illustrato come gestire gli spazi dei nomi specificati nell'origine del binding XML.</span><span class="sxs-lookup"><span data-stu-id="4069e-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="4069e-105">Se i dati XML hanno la definizione dello spazio dei nomi XML seguente:</span><span class="sxs-lookup"><span data-stu-id="4069e-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="4069e-106">È possibile usare l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> per eseguire il mapping dello spazio dei nomi a una <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4069e-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="4069e-107">È quindi possibile utilizzare il <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="4069e-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="4069e-108">Il <xref:System.Windows.Controls.ListBox> in questo esempio Visualizza il *titolo* e il controller di dominio *: data* di ogni *elemento*.</span><span class="sxs-lookup"><span data-stu-id="4069e-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="4069e-109">Si noti che la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificata non deve corrispondere a quella utilizzata nell'origine XML. Se il prefisso viene modificato nell'origine XML, il mapping continua a funzionare.</span><span class="sxs-lookup"><span data-stu-id="4069e-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="4069e-110">In questo particolare esempio, i dati XML provengono da un servizio Web, ma l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> funziona anche con dati XML o XML inline in un file incorporato.</span><span class="sxs-lookup"><span data-stu-id="4069e-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="4069e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4069e-111">See also</span></span>

- [<span data-ttu-id="4069e-112">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="4069e-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="4069e-113">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="4069e-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="4069e-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="4069e-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
