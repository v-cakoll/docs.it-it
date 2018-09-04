---
title: 'Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 99bfcd96dea1bb92866127095a422003bf01f7cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506874"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione
Windows Form <xref:System.Windows.Forms.Panel> controlli vengono utilizzati per raggruppare altri controlli. Esistono tre motivi per i controlli di gruppo. Uno è visual raggruppamento di elementi di form per un'interfaccia utente non crittografato. un vantaggio è a livello di codice di raggruppamento, dei pulsanti di opzione, ad esempio; l'ultimo è per spostare i controlli in un'unità in fase di progettazione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-group-of-controls"></a>Per creare un gruppo di controlli  
  
1.  Trascinare un <xref:System.Windows.Forms.Panel> controllare dal **Windows Forms** scheda della casella degli strumenti in un form.  
  
2.  Aggiungere altri controlli nel pannello per ognuno all'interno del Pannello di disegno.  
  
     Se si dispone di controlli esistenti che si desidera inserire in un pannello, è possibile selezionare tutti i controlli, li tagliare negli Appunti, selezionare il <xref:System.Windows.Forms.Panel> controllare e quindi incollarli nella casella di gruppo. È anche possibile trascinarli nel pannello.  
  
3.  (Facoltativo) Se si desidera aggiungere un bordo a un pannello, impostare il <xref:System.Windows.Forms.BorderStyle> proprietà. Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, e <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panoramica sul controllo Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Procedura: Impostare lo sfondo di un controllo Panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
