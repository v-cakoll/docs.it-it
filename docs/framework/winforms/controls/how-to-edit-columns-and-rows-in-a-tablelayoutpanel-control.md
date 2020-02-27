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
ms.openlocfilehash: 4473b20eea57088104a51eb1b6c080219223d214
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628644"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Procedura: modificare colonne e righe in un controllo TableLayoutPanel

Per modificare le righe e le colonne dei controlli, è possibile usare l'editor della raccolta del controllo <xref:System.Windows.Forms.TableLayoutPanel>, denominato finestra di dialogo **stili colonna e riga** .

> [!NOTE]
> Se si desidera che un controllo si estenda su più righe o colonne, impostare le proprietà `RowSpan` e `ColumnSpan` sul controllo. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).
>
> Se si desidera allineare un controllo all'interno di una cella o se si desidera che un controllo si estenda all'interno di una cella, utilizzare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del controllo. Per altre informazioni, vedere [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).

## <a name="to-edit-rows-and-columns"></a>Per modificare righe e colonne

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Fare clic sul glifo delle azioni della finestra di progettazione del controllo <xref:System.Windows.Forms.TableLayoutPanel> (![Small Black Arrow](./media/designer-actions-glyph.gif)) e selezionare **modifica righe e colonne** per aprire la finestra di dialogo **stili colonna e riga** . È anche possibile fare clic con il pulsante destro del mouse sul controllo <xref:System.Windows.Forms.TableLayoutPanel> e scegliere **modifica righe e colonne** dal menu di scelta rapida.

3. Per aggiungere o rimuovere colonne, selezionare le **colonne** nella casella di riepilogo a discesa **tipo di membro** .

4. Per aggiungere o rimuovere righe, selezionare **righe** dall'elenco a discesa **tipo di membro** .

5. Fare clic sul pulsante **Aggiungi** per aggiungere una riga o una colonna alla fine dell'elenco dei **membri** .

6. Fare clic sul pulsante **Inserisci** per aggiungere una riga o una colonna prima dell'elemento attualmente selezionato nell'elenco.

7. Se si aggiunge una riga o una colonna, selezionare il **tipo di dimensione** per la nuova riga o colonna. Per altre informazioni, vedere <xref:System.Windows.Forms.SizeType>.

8. Per rimuovere una riga o una colonna, fare clic sul pulsante **Rimuovi** per eliminare l'elemento attualmente selezionato nell'elenco dei **membri** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SizeType>
- [Controllo TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
