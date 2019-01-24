---
title: 'Procedura: Creare un elemento griglia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: b5bb9572b6a34b21208a8d8c0583068873772aae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726598"
---
# <a name="how-to-create-a-grid-element"></a>Procedura: Creare un elemento griglia
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare e usare un'istanza di <xref:System.Windows.Controls.Grid> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o code. In questo esempio Usa tre <xref:System.Windows.Controls.ColumnDefinition> gli oggetti e tre <xref:System.Windows.Controls.RowDefinition> oggetti per creare una griglia che ha nove celle, ad esempio in un foglio di lavoro. Ogni cella contiene un <xref:System.Windows.Controls.TextBlock> l'elemento che rappresenta i dati e la riga superiore contiene una <xref:System.Windows.Controls.TextBlock> con il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà applicato. Per visualizzare i limiti di ogni cella, il <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà è abilitata.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Entrambi gli approcci genererà un'interfaccia utente che risulta molto lo stesso, come quello riportato di seguito.

  ![una schermata illustra un'interfaccia utente WPF che contiene una griglia suddivisa in tre colonne.  Assuma l'intestazione '2018 prodotti spediti' che si estende su tutte le colonne della prima riga e ha tre colonne ciascuna con cifre di vendita per un determinato trimestre.  La riga inferiore è il testo che si estende su due colonne con il messaggio "Total Units: 300,000'](./media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Grid>
- [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
