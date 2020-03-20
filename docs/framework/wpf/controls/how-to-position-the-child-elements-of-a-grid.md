---
title: 'Procedura: posizionare gli elementi figlio di una griglia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186715"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Procedura: posizionare gli elementi figlio di una griglia
In questo esempio viene illustrato come utilizzare i <xref:System.Windows.Controls.Grid> metodi get e set definiti per posizionare gli elementi figlio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Grid> definito`grid1`un elemento padre ( ) con tre colonne e tre righe. Un <xref:System.Windows.Shapes.Rectangle> elemento`rect1`figlio ( ) <xref:System.Windows.Controls.Grid> viene aggiunto alla posizione in colonna zero, la posizione della riga zero. <xref:System.Windows.Controls.Button>gli elementi rappresentano metodi che possono <xref:System.Windows.Shapes.Rectangle> essere <xref:System.Windows.Controls.Grid>chiamati per riposizionare l'elemento all'interno di . Quando un utente fa clic su un pulsante, viene attivato il metodo correlato.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Nell'esempio code-behind seguente vengono <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestiti i metodi che generano gli eventi del pulsante. L'esempio scrive queste <xref:System.Windows.Controls.TextBlock> chiamate al metodo negli elementi che usano metodi get correlati per restituire i nuovi valori delle proprietà come stringhe.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Ecco il risultato finale!

 ![una schermata illustra un'interfaccia utente WPF con due colonne, il lato destro ha una griglia 3 x 3 e la sinistra ha pulsanti per spostare un rettangolo colorato tra le colonne e le righe della griglia](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
