---
title: Puntatori del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740951"
---
# <a name="mouse-pointers-in-windows-forms"></a>Puntatori del mouse in Windows Form
Il *puntatore*del mouse, a volte indicato come cursore, è una bitmap che specifica un punto di interesse sullo schermo per l'input dell'utente con il mouse. In questo argomento viene fornita una panoramica del puntatore del mouse in Windows Forms e vengono descritti alcuni dei modi per modificare e controllare il puntatore del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>Accesso al puntatore del mouse  
 Il puntatore del mouse è rappresentato dalla classe <xref:System.Windows.Forms.Cursor> e ogni <xref:System.Windows.Forms.Control> dispone di una proprietà <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> che specifica il puntatore per il controllo. La classe <xref:System.Windows.Forms.Cursor> contiene proprietà che descrivono il puntatore, ad esempio le proprietà <xref:System.Windows.Forms.Cursor.Position%2A> e <xref:System.Windows.Forms.Cursor.HotSpot%2A> e i metodi che possono modificare l'aspetto del puntatore, ad esempio i metodi <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>e <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## <a name="controlling-the-mouse-pointer"></a>Controllo del puntatore del mouse  
 In alcuni casi può essere opportuno limitare l'area in cui è possibile utilizzare il puntatore del mouse o modificare la posizione del mouse. È possibile ottenere o impostare la posizione corrente del mouse usando la proprietà <xref:System.Windows.Forms.Cursor.Position%2A> della <xref:System.Windows.Forms.Cursor>. Inoltre, è possibile limitare l'area in cui è possibile utilizzare il puntatore del mouse impostando la proprietà <xref:System.Windows.Forms.Cursor.Clip%2A>. Per impostazione predefinita, l'area di ritaglio è l'intera schermata.  
  
## <a name="changing-the-mouse-pointer"></a>Modifica del puntatore del mouse  
 La modifica del puntatore del mouse è un modo importante per fornire commenti e suggerimenti all'utente. Il puntatore del mouse, ad esempio, può essere modificato nei gestori del <xref:System.Windows.Forms.Control.MouseEnter> e <xref:System.Windows.Forms.Control.MouseLeave> eventi per indicare all'utente che i calcoli sono in corso e per limitare l'interazione dell'utente nel controllo. In alcuni casi, il puntatore del mouse verrà modificato a causa di eventi di sistema, ad esempio quando l'applicazione è in esecuzione in un'operazione di trascinamento della selezione.  
  
 Il modo principale per modificare il puntatore del mouse consiste nell'impostare la proprietà <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Control.DefaultCursor%2A> di un controllo su un nuovo <xref:System.Windows.Forms.Cursor>. Per esempi relativi alla modifica del puntatore del mouse, vedere l'esempio di codice nella classe <xref:System.Windows.Forms.Cursor>. Inoltre, la classe <xref:System.Windows.Forms.Cursors> espone un set di oggetti <xref:System.Windows.Forms.Cursor> per molti tipi diversi di puntatori, ad esempio un puntatore simile a una mano. Per visualizzare il puntatore di attesa, simile a una clessidra, ogni volta che il puntatore del mouse si trova sul controllo, utilizzare la proprietà <xref:System.Windows.Forms.Control.UseWaitCursor%2A> della classe <xref:System.Windows.Forms.Control>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Cursor>
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Funzionalità di trascinamento della selezione in Windows Forms](drag-and-drop-functionality-in-windows-forms.md)
