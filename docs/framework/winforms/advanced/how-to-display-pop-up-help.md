---
title: 'Procedura: visualizzare la Guida rapida'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d139c283d002ac76005f22385d83190144c5082
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-pop-up-help"></a>Procedura: visualizzare la Guida rapida
È un modo per visualizzare la Guida in Windows Form tramite il **Guida** pulsante posizionate sul lato destro della barra del titolo, accessibile tramite la <xref:System.Windows.Forms.Form.HelpButton%2A> proprietà. Questo tipo di visualizzazione della Guida è ideale con le finestre di dialogo. Con le finestre di dialogo visualizzate come modali (con il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>) risulta difficile accedere a sistemi di Guida esterni, perché le finestre di dialogo modali devono venire chiuse prima che lo stato attivo possa passare a un'altra finestra. Inoltre, l'uso di **Guida** pulsante richiede che sia presente alcun **Riduci a icona** pulsante o **Ingrandisci** pulsante nella barra del titolo. Questa è una convenzione di dialogo standard, mentre i form dispongono in genere **Riduci a icona** e **Ingrandisci** pulsanti.  
  
 Tenere presente che è possibile usare anche il componente <xref:System.Windows.Forms.HelpProvider> per collegare i controlli ai file in un sistema di Guida, anche se è stata implementata la Guida rapida. Per ulteriori informazioni, vedere [visualizzazione della Guida in un'applicazione Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-pop-up-help"></a>Per visualizzare la Guida rapida  
  
1.  Trascinare un [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) componente dalla casella degli strumenti al form.  
  
     Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.  
  
2.  Nella finestra Proprietà impostare la proprietà <xref:System.Windows.Forms.Form.HelpButton%2A> su `true`. Sulla destra della barra del titolo del form verrà visualizzato un pulsante con un punto interrogativo.  
  
3.  Per visualizzare <xref:System.Windows.Forms.Form.HelpButton%2A>, è necessario impostare le proprietà <xref:System.Windows.Forms.Form.MinimizeBox%2A> e <xref:System.Windows.Forms.Form.MaximizeBox%2A> del form su `false`, la proprietà <xref:System.Windows.Forms.Form.ControlBox%2A> su `true` e la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> su uno dei valori seguenti: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.  
  
4.  Selezionare il controllo per il quale si desidera visualizzare la Guida nel form e impostare la stringa della Guida nella finestra Proprietà. Questa è la stringa di testo che verrà visualizzato in una finestra simile a un [descrizione comando](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).  
  
5.  Premere **F5**.  
  
6.  Premere il **Guida** pulsante sulla barra del titolo e fare clic sul controllo su cui impostare la stringa della Guida.  
  
## <a name="see-also"></a>Vedere anche  
 [Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrazione della Guida dell'utente in Windows Form](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Form](../../../../docs/framework/winforms/index.md)
