---
title: Coordinate di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: 6feabadff17538f4a7368c348f7b72226e2d678e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980655"
---
# <a name="windows-forms-coordinates"></a>Coordinate di Windows Form
Il sistema di coordinate di un modulo di Windows si basa su coordinate del dispositivo e l'unità di misura quando si disegnano in Windows Form base è l'unità di dispositivo (in genere, il pixel). I punti nella schermata sono descritti dalle coppie di coordinate x e y, con le coordinate x crescenti a destra e le coordinate y aumentano dall'alto verso il basso. Il percorso dell'entità origin, rispetto allo schermo, varia a seconda del fatto che siano specificate le coordinate dello schermo o client.  
  
## <a name="screen-coordinates"></a>Coordinate dello schermo  
 Un'applicazione Windows Forms specifica la posizione di una finestra sullo schermo in coordinate dello schermo. Per le coordinate dello schermo, l'origine è l'angolo superiore sinistro della schermata. La posizione completa di una finestra viene spesso descritta da un <xref:System.Drawing.Rectangle> struttura che contiene le coordinate dello schermo di due punti che definiscono gli angoli superiore sinistro e inferiore destro della finestra.  
  
## <a name="client-coordinates"></a>Coordinate del client  
 Un'applicazione Windows Forms consente di specificare la posizione dei punti in un form o controllo usando le coordinate del client. Origine per le coordinate del client è l'angolo superiore sinistro dell'area client del controllo o form. Coordinate del client assicurarsi che un'applicazione possa usare i valori delle coordinate coerente durante il disegno in un form o controllo, indipendentemente dalla posizione del form o controllo sullo schermo.  
  
 Le dimensioni dell'area client vengono anche descritte da un <xref:System.Drawing.Rectangle> struttura che contiene coordinate del client per l'area. In tutti i casi, la coordinata superiore sinistra del rettangolo è incluso nell'area client, mentre è esclusa la coordinata inferiore destro. Operazioni di grafica non includono i bordi destro e inferiore di un'area client. Ad esempio il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo si riempirà al bordo destro e inferiore del rettangolo specificato, ma non includerà questi bordi.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Mapping da un tipo di Coordinate a un altro  
 In alcuni casi, potrebbe essere necessario eseguire il mapping da coordinate dello schermo a coordinate del client. È possibile farlo facilmente usando le <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> metodi disponibili nel <xref:System.Windows.Forms.Control> classe. Ad esempio, il <xref:System.Windows.Forms.Control.MousePosition%2A> proprietà di <xref:System.Windows.Forms.Control> viene segnalato nelle coordinate dello schermo, ma è possibile la conversione in coordinate client.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
