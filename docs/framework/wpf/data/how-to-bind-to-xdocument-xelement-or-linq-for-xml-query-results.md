---
title: "Procedura: eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ to XML"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920118"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Procedura: eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ to XML

In questo esempio viene illustrato come associare dati XML a un <xref:System.Windows.Controls.ItemsControl> utilizzando <xref:System.Xml.Linq.XDocument>.

## <a name="example"></a>Esempio

Il codice XAML seguente definisce un <xref:System.Windows.Controls.ItemsControl> e include un modello di dati per i dati di tipo `Planet` nello spazio dei nomi `http://planetsNS` XML. Un tipo di dati XML che occupa uno spazio dei nomi deve includere lo spazio dei nomi tra parentesi graffe e, se viene visualizzato dove viene visualizzata un'estensione di markup XAML, deve precedere lo spazio dei nomi con una sequenza di escape in parentesi graffe. Questo codice viene associato a proprietà dinamiche che corrispondono ai metodi <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement>. Le proprietà dinamiche consentono al codice XAML di eseguire un'associazione a proprietà dinamiche che condividono i nomi dei metodi. Per altre informazioni, vedere [LINQ to XML proprietà dinamiche](linq-to-xml-dynamic-properties.md). Si noti che la dichiarazione predefinita dello spazio dei nomi per il codice XML non viene applicata ai nomi di attributo.

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

Il codice C# seguente chiama<xref:System.Xml.Linq.XDocument.Load%2A>e imposta il contesto dati del pannello dello stack su tutti i sottoelementi dell'elemento denominato`SolarSystemPlanets`nello spazio dei nomi`http://planetsNS`XML.

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

I dati XML possono essere archiviati come una risorsa XAML usando <xref:System.Windows.Data.ObjectDataProvider>. Per un esempio completo, vedere [codice sorgente L2DBForm. XAML](l2dbform-xaml-source-code.md). L'esempio seguente illustra come il codice può impostare il contesto dei dati per una risorsa oggetto.

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

Le proprietà dinamiche mappate a <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> forniscono flessibilità in XAML. Il codice può anche eseguire l'associazione ai risultati di una query LINQ to XML. Questo esempio esegue l'associazione ai risultati di una query ordinati in base al valore di un elemento.

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a>Vedere anche

- [Panoramica delle origini di associazione](binding-sources-overview.md)
- [Panoramica dei data binding WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Esempio di data binding WPF tramite LINQ to XML](linq-to-xml-data-binding-sample.md)
- [Proprietà dinamiche in LINQ to XML](linq-to-xml-dynamic-properties.md)
