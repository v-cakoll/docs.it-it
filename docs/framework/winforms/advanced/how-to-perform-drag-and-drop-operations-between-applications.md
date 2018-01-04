---
title: 'Procedura: eseguire operazioni di trascinamento e rilascio tra applicazioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 514c283575ca54e74d23ae31d3590979be2c3ef0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a>Procedura: eseguire operazioni di trascinamento e rilascio tra applicazioni
Eseguire operazioni di trascinamento della selezione tra applicazioni non è diverso dal consentire quest'azione nell'ambito di un'applicazione, purché entrambe le applicazioni implicate si comportino in base al "contratto" stabilito tra le proprietà <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> e <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
 Nella procedura seguente si userà un'applicazione basata su Windows creata dall'utente e l'elaboratore di testi WordPad incluso con il sistema operativo Windows per eseguire operazioni di trascinamento della selezione tra applicazioni. WordPad offre un determinato set di effetti consentiti per il trascinamento del testo selezionato; l'applicazione basata su Windows per cui si scriverà il codice interagirà con tali effetti, in modo che le operazioni di trascinamento della selezione possano essere completate correttamente.  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a>Per eseguire una procedura di trascinamento della selezione tra applicazioni  
  
1.  Creare una nuova applicazione Windows Form.  
  
2.  Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.  
  
3.  Configurare il controllo <xref:System.Windows.Forms.TextBox> per ricevere dati trascinati.  
  
     Per ulteriori informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento e rilascio in Windows Form](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Eseguire l'applicazione basata su Windows e, mentre l'applicazione è in esecuzione, eseguire WordPad.  
  
     WordPad è un editor di testo installato da Windows che consente operazioni di trascinamento della selezione. È accessibile premendo il **avviare** pulsante, la selezione di **eseguire**e quindi digitando `WordPad` nella casella di testo del **eseguire** la finestra di dialogo e fare clic su **OK**.  
  
5.  Una volta aperto WordPad, digitare una stringa di testo al suo interno.  
  
6.  Usando il mouse, selezionare il testo e quindi trascinarlo sul controllo <xref:System.Windows.Forms.TextBox> nell'applicazione basata su Windows.  
  
     Osservare che quando si passa il mouse sul controllo <xref:System.Windows.Forms.TextBox> (e, di conseguenza, si genera l'evento <xref:System.Windows.Forms.Control.DragEnter>), il cursore cambia ed è possibile rilasciare il testo selezionato sul controllo <xref:System.Windows.Forms.TextBox>.  
  
     È anche possibile configurare il controllo <xref:System.Windows.Forms.TextBox> per consentire il trascinamento delle stringhe di testo in WordPad. Per ulteriori informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento e rilascio in Windows Form](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Aggiungere dati agli Appunti](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [Procedura: Recuperare dati dagli Appunti](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
