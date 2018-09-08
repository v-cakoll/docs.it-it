---
title: 'Procedura: inserire righe e colonne in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 5363e7a7def8d2593d3ac474deb9d3d7b77d3912
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44136511"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedura: inserire righe e colonne in un controllo TableLayoutPanel
Controlli in un <xref:System.Windows.Forms.TableLayoutPanel> controllo può estendersi su righe e colonne adiacenti.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-span-columns-and-rows"></a>Per inserire righe e colonne  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllare dal **casella degli strumenti** nel form.  
  
2.  Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** alla cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
3.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda colonna.  
  
4.  Impostare il <xref:System.Windows.Forms.Button> del controllo **RowSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda riga.  
  
5.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **1**. Si noti che il <xref:System.Windows.Forms.Button> controllo si sposta nella prima colonna e si estende la prima e seconda riga.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
