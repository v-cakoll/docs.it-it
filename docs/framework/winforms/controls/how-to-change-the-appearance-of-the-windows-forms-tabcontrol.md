---
title: Modificare l'aspetto di TabControl
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746607"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Procedura: Modificare l'aspetto del controllo TabControl di Windows Form
È possibile modificare l'aspetto delle schede in Windows Forms usando le proprietà del <xref:System.Windows.Forms.TabControl> e gli oggetti <xref:System.Windows.Forms.TabPage> che costituiscono le singole schede del controllo. Impostando queste proprietà, è possibile visualizzare le immagini sulle schede, visualizzare le schede verticalmente anziché orizzontalmente, visualizzare più righe di schede e abilitare o disabilitare le schede a livello di codice.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Per visualizzare un'icona nella parte etichetta di una scheda  
  
1. Aggiungere un controllo <xref:System.Windows.Forms.ImageList> al form.  
  
2. Aggiungere immagini all'elenco di immagini.  
  
     Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TabControl.ImageList%2A> del <xref:System.Windows.Forms.TabControl> sul controllo <xref:System.Windows.Forms.ImageList>.  
  
4. Impostare la proprietà <xref:System.Windows.Forms.TabPage.ImageIndex%2A> della <xref:System.Windows.Forms.TabPage> sull'indice di un'immagine appropriata nell'elenco.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Per creare più righe di schede  
  
1. Aggiungere il numero di schede desiderate.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.TabControl.Multiline%2A> della <xref:System.Windows.Forms.TabControl> su `true`.  
  
3. Se le schede non sono già presenti in più righe, impostare la proprietà <xref:System.Windows.Forms.Control.Width%2A> della <xref:System.Windows.Forms.TabControl> in modo che sia più stretta di tutte le schede.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Per disporre le schede sul lato del controllo  
  
- Impostare la proprietà <xref:System.Windows.Forms.TabControl.Alignment%2A> della <xref:System.Windows.Forms.TabControl> su <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Per abilitare o disabilitare a livello di codice tutti i controlli in una scheda  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TabPage.Enabled%2A> della <xref:System.Windows.Forms.TabPage> su `true` o `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Per visualizzare le tabulazioni come pulsanti  
  
- Impostare la proprietà <xref:System.Windows.Forms.TabControl.Appearance%2A> della <xref:System.Windows.Forms.TabControl> su <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TabControl](tabcontrol-control-windows-forms.md)
- [Panoramica del controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: Aggiungere un controllo a un oggetto TabPage](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: Disabilitare le schede](how-to-disable-tab-pages.md)
- [Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
