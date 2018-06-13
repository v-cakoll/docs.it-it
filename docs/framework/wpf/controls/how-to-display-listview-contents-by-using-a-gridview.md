---
title: 'Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 103a439b9cee959d0077e5a759364eb9b943905d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554051"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView
In questo esempio viene illustrato come definire un <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È possibile definire la modalità di visualizzazione di un <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> oggetti. Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti associati per il contenuto dei dati specificato per il <xref:System.Windows.Controls.ListView> controllo. Questo <xref:System.Windows.Controls.GridView> esempio specifica tre <xref:System.Windows.Controls.GridViewColumn> gli oggetti che eseguono il mapping per il `FirstName`, `LastName`, e `EmployeeNumber` campi del `EmployeeInfoDataSource` che viene impostato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListView> controllo.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Nella figura seguente mostra come viene visualizzata in questo esempio.  
  
 ![ListView con output GridView ](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
