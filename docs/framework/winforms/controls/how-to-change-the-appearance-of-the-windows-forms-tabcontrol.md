---
title: "Procedura: Modificare l'aspetto di TabControl di Windows Forms"
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
ms.openlocfilehash: 05df05a52914f27a4b62cf7bde92e5d942b6ea06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904267"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Procedura: Modificare l'aspetto di TabControl di Windows Forms
È possibile modificare l'aspetto delle schede in Windows Form usando le proprietà del <xref:System.Windows.Forms.TabControl> e il <xref:System.Windows.Forms.TabPage> gli oggetti che costituiscono le singole schede nel controllo. L'impostazione di queste proprietà è possibile visualizzare le immagini nelle schede, visualizzare le schede in verticale, anziché in orizzontale, visualizzare più righe di schede e abilitare o disabilitare le schede a livello di codice.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Per visualizzare un'icona nella parte dell'etichetta di una scheda  
  
1. Aggiungere un <xref:System.Windows.Forms.ImageList> controllo al form.  
  
2. Aggiungere immagini all'elenco di immagini.  
  
     Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [come: Aggiungere o rimuovere immagini tramite il Windows Form componente ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3. Impostare il <xref:System.Windows.Forms.TabControl.ImageList%2A> proprietà del <xref:System.Windows.Forms.TabControl> per il <xref:System.Windows.Forms.ImageList> controllo.  
  
4. Impostare il <xref:System.Windows.Forms.TabPage.ImageIndex%2A> proprietà del <xref:System.Windows.Forms.TabPage> all'indice di un'immagine appropriata nell'elenco.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Per creare più righe di schede  
  
1. Aggiungere il numero di pagine di scheda desiderata.  
  
2. Impostare il <xref:System.Windows.Forms.TabControl.Multiline%2A> proprietà del <xref:System.Windows.Forms.TabControl> a `true`.  
  
3. Se le schede non è già visualizzata in più righe, impostare il <xref:System.Windows.Forms.Control.Width%2A> proprietà del <xref:System.Windows.Forms.TabControl> sia larghezza di tutte le schede.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Per disporre le schede sul lato del controllo  
  
-   Impostare il <xref:System.Windows.Forms.TabControl.Alignment%2A> proprietà del <xref:System.Windows.Forms.TabControl> al <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Per abilitare o disabilitare tutti i controlli in una scheda a livello di codice  
  
1. Impostare il <xref:System.Windows.Forms.TabPage.Enabled%2A> proprietà del <xref:System.Windows.Forms.TabPage> al `true` o `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Per visualizzare le schede sotto forma di pulsanti  
  
-   Impostare il <xref:System.Windows.Forms.TabControl.Appearance%2A> proprietà del <xref:System.Windows.Forms.TabControl> al <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TabControl](tabcontrol-control-windows-forms.md)
- [Panoramica del controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: Aggiungere un controllo a un oggetto TabPage](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: Disabilitare le schede](how-to-disable-tab-pages.md)
- [Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
