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
ms.openlocfilehash: 763d5df6c49d45f7ee305f4a3be0a1f0a2539872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533507"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Procedura: modificare colonne e righe in un controllo TableLayoutPanel
È possibile utilizzare l'editor della raccolta del <xref:System.Windows.Forms.TableLayoutPanel> controllo, ossia il **stili di riga e colonna** della finestra di dialogo per modificare le righe e colonne dei controlli.  
  
> [!NOTE]
>  Se si desidera un controllo per inserire più righe o colonne, impostare il `RowSpan` e `ColumnSpan` proprietà del controllo. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Se si desidera allineare un controllo all'interno di una cella o se si desidera un controllo per l'estensione in una cella, utilizzare il controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-edit-rows-and-columns"></a>Per modificare righe e colonne  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.  
  
2.  Fare clic su di <xref:System.Windows.Forms.TableLayoutPanel> glifo dello smart tag del controllo (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) e selezionare **Modifica righe e colonne** per aprire la  **Stili di riga e colonna** la finestra di dialogo. È anche possibile fare clic di <xref:System.Windows.Forms.TableLayoutPanel> controllo **Modifica righe e colonne** dal menu di scelta rapida.  
  
3.  Per aggiungere o rimuovere colonne, selezionare **colonne** dal **tipo di membro** casella di riepilogo a discesa.  
  
4.  Per aggiungere o rimuovere le righe, selezionare **righe** dal **tipo di membro** casella di riepilogo a discesa.  
  
5.  Fare clic su di **Aggiungi** pulsante per aggiungere una riga o colonna alla fine del **membro** elenco.  
  
6.  Fare clic su di **inserire** pulsante per aggiungere una riga o colonna prima dell'elemento attualmente selezionato nell'elenco.  
  
7.  Se si aggiunge una riga o colonna, selezionare il **tipo dimensione** per la nuova riga o colonna. Per altre informazioni, vedere <xref:System.Windows.Forms.SizeType>.  
  
8.  Per rimuovere una riga o colonna, scegliere il **rimuovere** pulsante per eliminare l'elemento attualmente selezionato nel **membro** elenco.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SizeType>  
 [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
