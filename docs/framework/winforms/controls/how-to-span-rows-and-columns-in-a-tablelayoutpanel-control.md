---
title: 'Procedura: Inserire righe e colonne in un controllo TableLayoutPanel'
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
ms.openlocfilehash: fdcb4bccefe814554148aaac6e2d42e49893b7e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685230"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedura: Inserire righe e colonne in un controllo TableLayoutPanel
Controlli in un <xref:System.Windows.Forms.TableLayoutPanel> controllo può estendersi su righe e colonne adiacenti.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-span-columns-and-rows"></a>Per inserire righe e colonne  
  
1.  Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.  
  
2.  Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** alla cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
3.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda colonna.  
  
4.  Impostare il <xref:System.Windows.Forms.Button> del controllo **RowSpan** proprietà **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda riga.  
  
5.  Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **1**. Si noti che il <xref:System.Windows.Forms.Button> controllo si sposta nella prima colonna e si estende la prima e seconda riga.  
  
## <a name="see-also"></a>Vedere anche
- [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
