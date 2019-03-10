---
title: 'Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 541e50a8ee9c5338acc7c5e347549fd03a0f6323
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710719"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione
È possibile impostare un <xref:System.Windows.Forms.ToolTip> stringa nel codice o nella finestra di progettazione Windows Form. Per altre informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Per impostare una descrizione comandi a livello di codice  
  
1.  Aggiungere il controllo che verrà visualizzata la descrizione comando.  
  
2.  Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Per impostare una descrizione comando nella finestra di progettazione  
  
1.  Aggiungere un componente <xref:System.Windows.Forms.ToolTip> al form.  
  
2.  Selezionare il controllo che consente di visualizzare la descrizione comando o aggiungerlo al form.  
  
3.  Nel **proprietà** impostare nella finestra di **descrizione comando su ToolTip1** valore da una stringa di testo appropriata.  

### <a name="to-remove-a-tooltip-programmatically"></a>Per rimuovere una descrizione comandi a livello di codice  
  
1.  Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a>Per rimuovere una descrizione comando nella finestra di progettazione  
  
1.  Selezionare il controllo che visualizza la descrizione comando.  
  
2.  Nel **delle proprietà** finestra, eliminare il testo nel **descrizione comando su ToolTip1**.  

## <a name="see-also"></a>Vedere anche
- [Panoramica sul componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Procedura: Modifica del ritardo del componente di descrizione comando di Windows Form](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [Componente ToolTip](tooltip-component-windows-forms.md)
