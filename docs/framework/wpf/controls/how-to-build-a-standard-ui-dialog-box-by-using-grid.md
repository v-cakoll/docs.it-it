---
title: "Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 57edaa173b85bc06c6859b08d3edec281e1b8942
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372858"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard utilizzando l'elemento Grid
In questo esempio viene illustrato come creare uno standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] finestra di dialogo tramite il <xref:System.Windows.Controls.Grid> elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una finestra di dialogo, ad esempio la **eseguiti** nella finestra di dialogo di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.  
  
 Nell'esempio viene creata una <xref:System.Windows.Controls.Grid> e Usa le <xref:System.Windows.Controls.ColumnDefinition> e <xref:System.Windows.Controls.RowDefinition> classi per definire cinque colonne e quattro righe.  
  
 L'esempio aggiunge quindi e posiziona un' <xref:System.Windows.Controls.Image>, `RunIcon.png`, per rappresentare l'immagine che si trova nella finestra di dialogo. L'immagine viene inserito nella colonna e riga del primo il <xref:System.Windows.Controls.Grid> (angolo in alto a sinistra).  
  
 Successivamente, nell'esempio viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento alla prima colonna, che si estende le colonne rimanenti della prima riga. Aggiunge un'altra <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga nella prima colonna, per rappresentare il **Open** casella di testo. Oggetto <xref:System.Windows.Controls.TextBlock> indicato di seguito, che rappresenta l'area di immissione dati.  
  
 Infine, l'esempio aggiunge tre <xref:System.Windows.Controls.Button> elementi nella riga finale, che rappresentano le **OK**, **Annulla**, e **Sfoglia** gli eventi.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure relative alle proprietà](grid-how-to-topics.md)
