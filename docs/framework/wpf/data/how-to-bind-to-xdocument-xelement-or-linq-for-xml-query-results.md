---
title: "Procedura: Esecuzione dell'associazione ai risultati di una query XDocument, XElement o LINQ to XML"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 6c220bf7b06e6eaf4cf661c07a0a8c6c37ec333d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358262"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Procedura: Esecuzione dell'associazione ai risultati di una query XDocument, XElement o LINQ to XML
In questo esempio viene illustrato come associare dati XML da un <xref:System.Windows.Controls.ItemsControl> usando <xref:System.Xml.Linq.XDocument>.  
  
## <a name="example"></a>Esempio  
 Il codice XAML seguente definisce un <xref:System.Windows.Controls.ItemsControl> e include un modello di dati di tipo `Planet` nel `http://planetsNS` spazio dei nomi XML. Un tipo di dati XML che occupa uno spazio dei nomi deve includere lo spazio dei nomi tra parentesi graffe e, se viene visualizzato dove viene visualizzata un'estensione di markup XAML, deve precedere lo spazio dei nomi con una sequenza di escape in parentesi graffe. Questo codice associa a proprietà dinamiche che corrispondono al <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> metodi del <xref:System.Xml.Linq.XElement> classe. Le proprietà dinamiche consentono al codice XAML di eseguire un'associazione a proprietà dinamiche che condividono i nomi dei metodi. Per altre informazioni, vedere [Proprietà dinamiche di LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties). Si noti che la dichiarazione predefinita dello spazio dei nomi per il codice XML non viene applicata ai nomi di attributo.  
  
 [!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Le chiamate di codice c# seguente <xref:System.Xml.Linq.XDocument.Load%2A> e imposta il contesto di dati del pannello stack su tutti i sottoelementi dell'elemento denominato `SolarSystemPlanets` nel `http://planetsNS` spazio dei nomi XML.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 Dati XML possono essere archiviati come risorsa XAML tramite <xref:System.Windows.Data.ObjectDataProvider>. Per un esempio completo, vedere [codice sorgente di L2DBForm.xaml](/visualstudio/designers/l2dbform-xaml-source-code). L'esempio seguente illustra come il codice può impostare il contesto dei dati per una risorsa oggetto.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Le proprietà dinamiche che eseguono il mapping a <xref:System.Xml.Linq.XContainer.Element%2A> e <xref:System.Xml.Linq.XElement.Attribute%2A> offrono flessibilità con XAML. Il codice può anche eseguire l'associazione ai risultati di una query LINQ to XML. Questo esempio esegue l'associazione ai risultati di una query ordinati in base al valore di un elemento.  
  
 [!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica delle origini di associazione](binding-sources-overview.md)
- [Panoramica dei data binding WPF con LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [Esempio di data binding WPF tramite LINQ to XML](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [Proprietà dinamiche in LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties)
