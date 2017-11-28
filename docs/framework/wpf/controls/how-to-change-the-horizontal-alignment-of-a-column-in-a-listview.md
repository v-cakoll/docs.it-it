---
title: 'Procedura: modificare l''allineamento orizzontale di una colonna in ListView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ed163de9a5b01a3ddab8ef42d21f38d35f48519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Procedura: modificare l'allineamento orizzontale di una colonna in ListView
Per impostazione predefinita, il contenuto di ogni colonna in un <xref:System.Windows.Controls.ListViewItem> allineato a sinistra. È possibile modificare l'allineamento di ogni colonna, fornendo un <xref:System.Windows.DataTemplate> e impostando il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dell'elemento all'interno di <xref:System.Windows.DataTemplate>. Questo argomento viene illustrato come un <xref:System.Windows.Controls.ListView> allineato il contenuto per impostazione predefinita e come modificare l'allineamento di una colonna in un <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i dati di `Title` e `ISBN` colonne è allineato a sinistra.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Per modificare l'allineamento del `ISBN` colonna, è necessario specificare che il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà di ogni <xref:System.Windows.Controls.ListViewItem> è <xref:System.Windows.HorizontalAlignment.Stretch>, in modo che gli elementi in ogni <xref:System.Windows.Controls.ListViewItem> può estendersi o essere posizionata lungo l'intera larghezza di ogni colonna. Poiché il <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare uno stile che imposta il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Successivamente, è necessario utilizzare un <xref:System.Windows.DataTemplate> per visualizzare il contenuto invece di usare il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà. Per visualizzare il `ISBN` di ogni modello, il <xref:System.Windows.DataTemplate> può contenere solo un <xref:System.Windows.Controls.TextBlock> con relativo <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà impostata su <xref:System.Windows.HorizontalAlignment.Right>.  
  
 L'esempio seguente definisce lo stile e <xref:System.Windows.DataTemplate> necessarie per rendere il `ISBN` colonna allineata a destra e la modifica di <xref:System.Windows.Controls.GridViewColumn> per fare riferimento il <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
