---
title: "Procedura: Visualizzare il contenuto dell'oggetto ListView tramite un oggetto GridView"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 1066869c80bf5bd87d656bcb4994c188ee0e8efc
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185610"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Procedura: Visualizzare il contenuto dell'oggetto ListView tramite un oggetto GridView
In questo esempio viene illustrato come definire un <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È possibile definire la modalità di visualizzazione di un <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> oggetti. Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti che associano il contenuto dei dati specificato per il <xref:System.Windows.Controls.ListView> controllo. Ciò <xref:System.Windows.Controls.GridView> esempio specifica tre <xref:System.Windows.Controls.GridViewColumn> negli oggetti mappati al `FirstName`, `LastName`, e `EmployeeNumber` campi del `EmployeeInfoDataSource` che viene impostato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListView> controllo.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente mostra come viene visualizzato in questo esempio.  
  
 ![Screenshot che mostra un ListView con output GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
- [Procedure relative alle proprietà](listview-how-to-topics.md)
