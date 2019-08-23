---
title: "Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard usando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923412"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard usando l'elemento Grid
Questo esempio illustra come creare una finestra di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialogo standard usando l' <xref:System.Windows.Controls.Grid> elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una finestra di dialogo come la finestra di dialogo **Esegui** nel sistema operativo Windows.  
  
 Nell'esempio viene creato <xref:System.Windows.Controls.Grid> un oggetto e <xref:System.Windows.Controls.ColumnDefinition> vengono <xref:System.Windows.Controls.RowDefinition> utilizzate le classi e per definire cinque colonne e quattro righe.  
  
 Nell'esempio viene quindi aggiunto e posizionato <xref:System.Windows.Controls.Image>un `RunIcon.png`oggetto,, per rappresentare l'immagine presente nella finestra di dialogo. L'immagine viene posizionata nella prima colonna e nella prima riga <xref:System.Windows.Controls.Grid> di (angolo superiore sinistro).  
  
 Successivamente, nell'esempio viene aggiunto <xref:System.Windows.Controls.TextBlock> un elemento alla prima colonna, che si estende sulle colonne rimanenti della prima riga. Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga della prima colonna, per rappresentare la casella di testo **aperta** . <xref:System.Windows.Controls.TextBlock> Segue, che rappresenta l'area di immissione dati.  
  
 Infine, nell'esempio vengono aggiunti <xref:System.Windows.Controls.Button> tre elementi alla riga finale, che rappresentano gli eventi **OK**, **Cancel**e **Browse** .  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure relative alle proprietà](grid-how-to-topics.md)
