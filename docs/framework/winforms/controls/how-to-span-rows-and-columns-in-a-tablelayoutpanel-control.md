---
title: 'Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel'
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
ms.openlocfilehash: 2b2a46bf53dd6ec9bc93a74cca37dffaaaf79751
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193135"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel
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

- [Controllo TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
