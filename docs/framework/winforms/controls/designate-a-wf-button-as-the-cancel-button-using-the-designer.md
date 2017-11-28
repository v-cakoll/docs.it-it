---
title: 'Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28e1667d086f26759e0129fc62d94ea79c68d880
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento. Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo nel form ha lo stato attivo, viene scelto un pulsante Annulla. Il pulsante di annullamento viene in genere programmato per consentire all'utente di abbandonare l'operazione senza intraprendere alcuna azione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-designate-the-cancel-button"></a>Per designare il pulsante Annulla  
  
1.  Selezionare il form in cui risiede il pulsante.  
  
2.  Nel **proprietà** finestra, imposta la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Panoramica sul controllo Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Modalità di selezione di un controllo Button di Windows Form](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Controllo Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
