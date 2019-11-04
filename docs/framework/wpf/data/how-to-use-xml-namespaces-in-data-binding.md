---
title: "Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460310"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati
## <a name="example"></a>Esempio
 Questo esempio spiega come gestire gli spazi dei nomi specificati nell'origine del binding [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].

 Se i dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] presentano la definizione dello spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] seguente:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 È possibile usare l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> per eseguire il mapping dello spazio dei nomi a una <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, come nell'esempio seguente. È quindi possibile usare il <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Il <xref:System.Windows.Controls.ListBox> in questo esempio Visualizza il *titolo* e il controller di dominio *: data* di ogni *elemento*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Si noti che la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificata non deve corrispondere a quella utilizzata nell'origine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]; Se il prefisso viene modificato nell'origine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] il mapping continua a funzionare.

 In questo particolare esempio, i dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] provengono da un servizio Web, ma l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> funziona anche con dati inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] o [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] in un file incorporato.

## <a name="see-also"></a>Vedere anche

- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
