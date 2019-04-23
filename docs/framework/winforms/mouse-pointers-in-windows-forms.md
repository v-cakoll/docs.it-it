---
title: Puntatori del mouse in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: e9b572ba40618a72b8db58917008ebd61a23de79
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122785"
---
# <a name="mouse-pointers-in-windows-forms"></a>Puntatori del mouse in Windows Form
Il puntatore del mouse *puntatore*, talvolta detta il cursore è una bitmap che specifica un punto di stato attivo nella schermata di input dell'utente con il mouse. Questo argomento viene fornita una panoramica del puntatore del mouse in Windows Forms e illustra alcuni dei modi per modificare e controllare il puntatore del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>L'accesso al puntatore del Mouse  
 Il puntatore del mouse è rappresentato dal <xref:System.Windows.Forms.Cursor> classe e ognuno <xref:System.Windows.Forms.Control> ha una <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> proprietà che specifica il puntatore per il controllo. Il <xref:System.Windows.Forms.Cursor> classe contiene proprietà che descrivono il puntatore, ad esempio il <xref:System.Windows.Forms.Cursor.Position%2A> e <xref:System.Windows.Forms.Cursor.HotSpot%2A> proprietà e metodi che è possano modificare l'aspetto dell'indicatore di misura, ad esempio il <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, e <xref:System.Windows.Forms.Cursor.DrawStretched%2A> metodi.  
  
## <a name="controlling-the-mouse-pointer"></a>Controllare il puntatore del Mouse  
 In alcuni casi è consigliabile limitare l'area in cui il puntatore del mouse può essere utilizzato o modificare la posizione del mouse. È possibile ottenere o impostare la posizione corrente del mouse tramite il <xref:System.Windows.Forms.Cursor.Position%2A> proprietà del <xref:System.Windows.Forms.Cursor>. Inoltre, è possibile limitare l'area può essere utilizzato il puntatore del mouse opzione offre il <xref:System.Windows.Forms.Cursor.Clip%2A> proprietà. Per impostazione predefinita, l'area di visualizzazione è l'intera schermata.  
  
## <a name="changing-the-mouse-pointer"></a>Modifica il puntatore del Mouse  
 Modifica il puntatore del mouse è un aspetto importante di come inviare un feedback all'utente. Ad esempio, il puntatore del mouse può essere modificato nei gestori del <xref:System.Windows.Forms.Control.MouseEnter> e <xref:System.Windows.Forms.Control.MouseLeave> eventi comunica all'utente che si verificano i calcoli e limitare l'interazione dell'utente nel controllo. In alcuni casi, il puntatore del mouse verrà modificato a causa di eventi di sistema, ad esempio quando l'applicazione è coinvolto in un'operazione di trascinamento e rilascio.  
  
 Il modo principale per modificare il puntatore del mouse consiste nell'impostare il <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> oppure <xref:System.Windows.Forms.Control.DefaultCursor%2A> proprietà di un controllo a un nuovo <xref:System.Windows.Forms.Cursor>. Per esempi di modifica il puntatore del mouse, vedere l'esempio di codice il <xref:System.Windows.Forms.Cursor> classe. Inoltre, il <xref:System.Windows.Forms.Cursors> classe espone un set di <xref:System.Windows.Forms.Cursor> oggetti per molti tipi diversi di puntatori, ad esempio un puntatore che rappresenta una mano. Per visualizzare il puntatore di attesa, che è simile a una clessidra, ogni volta che si trova il puntatore del mouse sul controllo, usare il <xref:System.Windows.Forms.Control.UseWaitCursor%2A> proprietà del <xref:System.Windows.Forms.Control> classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Cursor>
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Funzionalità di trascinamento della selezione in Windows Forms](drag-and-drop-functionality-in-windows-forms.md)
