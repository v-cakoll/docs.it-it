---
title: 'Procedura: Riassegnare i controlli esistenti a un padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: fa1bd6c0274fdf702072e062e6eeab7078375491
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600284"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedura: Riassegnare i controlli esistenti a un padre diverso
È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>Per riassegnare i controlli esistenti a un padre diverso  
  
1.  Trascinare i tre controlli <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.  
  
     Posizionarli uno accanto a altro, ma lasciarli non allineati.  
  
2.  Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
     Non trascinare l'icona nel form.  
  
3.  Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .  
  
     Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.  
  
4.  Fare clic e tenere premuto il pulsante del mouse.  
  
5.  Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
6.  Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .  
  
7.  Rilasciare il pulsante del mouse.  
  
     I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
