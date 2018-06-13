---
title: "Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551882"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid
In questo esempio viene illustrato come creare uno standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] la finestra di dialogo utilizzando il <xref:System.Windows.Controls.Grid> elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una finestra di dialogo come il **eseguire** nella finestra di dialogo di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.  
  
 Nell'esempio viene creato un <xref:System.Windows.Controls.Grid> e utilizza il <xref:System.Windows.Controls.ColumnDefinition> e <xref:System.Windows.Controls.RowDefinition> classi per definire cinque colonne e quattro righe.  
  
 Nell'esempio viene quindi aggiunto e posiziona un <xref:System.Windows.Controls.Image>, `RunIcon.png`, per rappresentare l'immagine che viene trovato nella finestra di dialogo. L'immagine viene posizionata nella prima colonna e riga del <xref:System.Windows.Controls.Grid> (nell'angolo superiore sinistro).  
  
 In seguito, viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento per la prima colonna, che si estende le colonne rimanenti della prima riga. Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento della seconda riga nella prima colonna, per rappresentare il **aprire** casella di testo. Oggetto <xref:System.Windows.Controls.TextBlock> indicato di seguito, che rappresenta l'area di immissione dati.  
  
 Infine, l'esempio aggiunge tre <xref:System.Windows.Controls.Button> elementi per la riga finale, che rappresentano il **OK**, **Annulla**, e **Sfoglia** eventi.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
