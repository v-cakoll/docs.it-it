---
title: 'Procedura: modificare colonne e righe in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 820d2f98290650bfaf377bd2d4b863dfb2e6e704
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500784"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Procedura: modificare colonne e righe in un controllo TableLayoutPanel
È possibile usare l'editor della raccolta del <xref:System.Windows.Forms.TableLayoutPanel> controllo, ossia il **stili di riga e colonna** della finestra di dialogo per modificare le righe e colonne dei controlli.  
  
> [!NOTE]
>  Se si vuole un controllo per estendersi su più righe o colonne, impostare il `RowSpan` e `ColumnSpan` proprietà sul controllo. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Se si desidera allineare un controllo all'interno di una cella o se si desidera un controllo da estendere all'interno di una cella, usare il controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-edit-rows-and-columns"></a>Per modificare righe e colonne  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllare dal **casella degli strumenti** nel form.  
  
2.  Scegliere il <xref:System.Windows.Forms.TableLayoutPanel> glifo smart tag del controllo (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Modifica righe e colonne** per aprire il  **Stili di riga e colonna** nella finestra di dialogo. È possibile anche con il pulsante destro selezionare la <xref:System.Windows.Forms.TableLayoutPanel> controllo e scegliere **Modifica righe e colonne** dal menu di scelta rapida.  
  
3.  Per aggiungere o rimuovere colonne, selezionare **colonne** dalle **tipo di membro** casella di riepilogo a discesa.  
  
4.  Per aggiungere o rimuovere righe, selezionare **righe** dalle **tipo di membro** casella di riepilogo a discesa.  
  
5.  Fare clic sui **Add** per aggiungere una riga o colonna alla fine della **membro** elenco.  
  
6.  Fare clic sui **Inserisci** pulsante per aggiungere una riga o colonna prima dell'elemento attualmente selezionato nell'elenco.  
  
7.  Se si aggiunge una riga o colonna, selezionare la **tipo di dimensione** per la nuova riga o colonna. Per altre informazioni, vedere <xref:System.Windows.Forms.SizeType>.  
  
8.  Per rimuovere una riga o colonna, scegliere il **rimuovere** pulsante per eliminare l'elemento attualmente selezionato nel **membro** elenco.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SizeType>  
 [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
