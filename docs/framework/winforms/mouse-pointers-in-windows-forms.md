---
title: Puntatori del mouse in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fb0e193ccbced719f30ede91cb59cd51dd349a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mouse-pointers-in-windows-forms"></a>Puntatori del mouse in Windows Form
Il puntatore del mouse *puntatore*, talvolta detto, il cursore è una bitmap che specifica un punto di stato attivo nella schermata per l'input dell'utente con il mouse. In questo argomento viene fornita una panoramica del puntatore del mouse in Windows Form e vengono descritti alcuni modi per modificare e controllare il puntatore del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>L'accesso il puntatore del Mouse  
 Il puntatore del mouse è rappresentato dal <xref:System.Windows.Forms.Cursor> classe e ogni <xref:System.Windows.Forms.Control> ha un <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> proprietà che specifica il puntatore per il controllo. Il <xref:System.Windows.Forms.Cursor> classe contiene proprietà che descrivono il puntatore, ad esempio il <xref:System.Windows.Forms.Cursor.Position%2A> e <xref:System.Windows.Forms.Cursor.HotSpot%2A> proprietà e metodi che è possono modificare l'aspetto dell'indicatore di misura, ad esempio il <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, e <xref:System.Windows.Forms.Cursor.DrawStretched%2A> metodi.  
  
## <a name="controlling-the-mouse-pointer"></a>Controllare il puntatore del Mouse  
 Può talvolta si desidera limitare l'area in cui il puntatore del mouse, può essere utilizzato o modificare la posizione del mouse. È possibile ottenere o impostare la posizione corrente del mouse, utilizzare il <xref:System.Windows.Forms.Cursor.Position%2A> proprietà del <xref:System.Windows.Forms.Cursor>. Inoltre, è possibile limitare l'area è possibile utilizzare il puntatore del mouse impostazione di <xref:System.Windows.Forms.Cursor.Clip%2A> proprietà. Per impostazione predefinita, l'area di visualizzazione è l'intero schermo.  
  
## <a name="changing-the-mouse-pointer"></a>Modifica il puntatore del Mouse  
 Modifica il puntatore del mouse è un aspetto importante di inviare commenti e suggerimenti per l'utente. Ad esempio, il puntatore del mouse può essere modificato nei gestori del <xref:System.Windows.Forms.Control.MouseEnter> e <xref:System.Windows.Forms.Control.MouseLeave> gli eventi per informare l'utente che si verificano i calcoli e per limitare l'interazione dell'utente nel controllo. In alcuni casi, il puntatore del mouse verrà modificato a causa di eventi di sistema, ad esempio quando l'applicazione è coinvolto in un'operazione di trascinamento e rilascio.  
  
 La modalità principale per modificare il puntatore del mouse è impostando il <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Control.DefaultCursor%2A> proprietà di un controllo a un nuovo <xref:System.Windows.Forms.Cursor>. Per esempi di quando il puntatore del mouse, vedere l'esempio di codice la <xref:System.Windows.Forms.Cursor> classe. Inoltre, il <xref:System.Windows.Forms.Cursors> classe espone un set di <xref:System.Windows.Forms.Cursor> oggetti per molti tipi diversi di puntatori, ad esempio un puntatore che è simile a una mano. Per visualizzare il puntatore di attesa, rappresentato da una clessidra, ogni volta che il puntatore del mouse sul controllo, utilizzare il <xref:System.Windows.Forms.Control.UseWaitCursor%2A> proprietà la <xref:System.Windows.Forms.Control> classe.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Cursor>  
 [Input del mouse in un'applicazione Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Funzionalità di trascinamento della selezione in Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
