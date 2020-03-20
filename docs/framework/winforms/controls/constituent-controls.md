---
title: Controlli costitutivi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182420"
---
# <a name="constituent-controls"></a>Controlli costitutivi
I controlli che costituiscono un controllo utente, detti anche *controlli costitutivi*, offrono scarsa flessibilità in termini di rendering personalizzato della grafica. Tutti i controlli Windows Form gestiscono <xref:System.Windows.Forms.Control.OnPaint%2A> il proprio rendering tramite il proprio metodo. Poiché questo metodo è protetto, non è accessibile allo sviluppatore e quindi non è possibile evitarne l'esecuzione quando il controllo viene disegnato. Ciò non implica tuttavia che non sia possibile aggiungere codice per modificare l'aspetto dei controlli costitutivi. Per eseguire un altro rendering, è possibile aggiungere un gestore eventi. Si supponga, ad esempio, di creare un <xref:System.Windows.Forms.UserControl> con un pulsante denominato `MyButton`. Se si desidera disporre di un rendering <xref:System.Web.UI.WebControls.Button>aggiuntivo oltre a quello fornito da , è necessario aggiungere codice al controllo utente simile al seguente:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> Alcuni controlli Windows Form, ad <xref:System.Windows.Forms.TextBox>esempio , vengono disegnati direttamente da Windows. In questi casi, il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo non viene mai chiamato e pertanto l'esempio precedente non verrà mai chiamato.  
  
 Viene quindi creato un metodo eseguito ogni volta che viene eseguito l'evento `MyButton.Paint`, aggiungendo in tal modo un'altra rappresentazione grafica al controllo. Si noti che ciò non impedisce l'esecuzione di `MyButton.OnPaint` e quindi tutti i disegni eseguiti normalmente da un pulsante continueranno a essere eseguiti in aggiunta al disegno personalizzato. Per informazioni dettagliate sulla tecnologia GDI+ e sul rendering personalizzato, vedere [Creazione di immagini grafiche con GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md). Per avere una rappresentazione univoca del controllo, è consigliabile creare un controllo ereditato per cui scrivere il codice di rendering personalizzato. Per informazioni dettagliate, vedere [Controlli creati dall'utente](user-drawn-controls.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Controlli creati dall'utente](user-drawn-controls.md)
- [Procedura: creare oggetti Graphics per disegnare](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
