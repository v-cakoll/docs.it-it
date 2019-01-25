---
title: Rendering di un controllo Windows Form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 9d2cb5041fbceb2e5c2d35d37a2001deffab40d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659371"
---
# <a name="rendering-a-windows-forms-control"></a>Rendering di un controllo Windows Form
Per il rendering si riferisce al processo di creazione di una rappresentazione visiva sullo schermo dell'utente. Windows Form usa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (la nuova libreria grafica di Windows) per il rendering. Le classi gestite che forniscono l'accesso al [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] sono nel <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi e relativi sottospazi dei nomi.  
  
 I seguenti elementi coinvolti nel rendering di controlli:  
  
-   Le funzionalità di disegno fornite dalla classe di base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
-   Gli elementi essenziali del [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] libreria grafica.  
  
-   La geometria dell'area di disegno.  
  
-   La procedura per liberare le risorse grafiche.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funzionalità di disegno fornite dal controllo  
 La classe di base <xref:System.Windows.Forms.Control> fornisce funzionalità di disegno tramite relativo <xref:System.Windows.Forms.Control.Paint> evento. Genera un controllo di <xref:System.Windows.Forms.Control.Paint> evento ogni volta che deve aggiornare la relativa visualizzazione. Per altre informazioni sugli eventi in .NET Framework, vedere [la gestione e generazione di eventi](../../../../docs/standard/events/index.md).  
  
 I dati dell'evento classe per il <xref:System.Windows.Forms.Control.Paint> evento <xref:System.Windows.Forms.PaintEventArgs>, contiene i dati necessari per la creazione di un controllo, ovvero un handle per un oggetto grafico e un oggetto rettangolo che rappresenta l'area da disegnare all'interno. Questi oggetti vengono visualizzati grassetto nel seguente frammento di codice.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics> è una classe gestita che incapsula la funzionalità di disegno, come descritto nella discussione di [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] più avanti in questo argomento. Il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> è un'istanza del <xref:System.Drawing.Rectangle> strutturare e definisce l'area disponibile per il disegno di un controllo. Gli sviluppatori di controlli è possono calcolare le <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> utilizzando il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di geometria più avanti in questo argomento.  
  
 Un controllo deve fornire la logica di rendering eseguendo l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo che eredita da <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> Ottiene l'accesso a un oggetto grafico e un rettangolo da disegnare tramite il <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> e il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> le proprietà del <xref:System.Windows.Forms.PaintEventArgs> istanza passata a esso.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di base <xref:System.Windows.Forms.Control> classe non implementa alcuna funzionalità di disegno, ma semplicemente che richiama i delegati di eventi registrati con il <xref:System.Windows.Forms.Control.Paint> evento. Quando esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A>, in genere, deve richiamare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base in modo che i delegati registrati ricevano il <xref:System.Windows.Forms.Control.Paint> evento. Tuttavia, i controlli che l'intera superficie di disegno non devono richiamare la classe di base <xref:System.Windows.Forms.Control.OnPaint%2A>, in quanto si verificherebbe lo sfarfallio. Per un esempio di override di <xref:System.Windows.Forms.Control.OnPaint%2A> eventi, vedere il [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo; in alternativa, richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo (ereditato da <xref:System.Windows.Forms.Control>) o un altro metodo che richiama <xref:System.Windows.Forms.Control.Invalidate%2A>. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo richiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A>. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo viene sottoposto a overload e, a seconda di argomenti forniti al <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un controllo viene ridisegnata alcuni o tutti i relativi area dello schermo.  
  
 La base <xref:System.Windows.Forms.Control> classe definisce un altro metodo è utile per il disegno, ovvero il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> (metodo).  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Disegna lo sfondo (e pertanto la forma) della finestra e viene garantito che sia veloce, mentre <xref:System.Windows.Forms.Control.OnPaint%2A> disegna i dettagli e può risultare più lento perché le richieste di disegno individuali vengono combinate in un <xref:System.Windows.Forms.Control.Paint> eventi che vengono trattate tutte le aree che devono essere ridisegnato. È possibile richiamare il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si vuole disegnare uno sfondo sfumature di colore per il controllo.  
  
 Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> dispone di un'evento simile alla nomenclatura e accetta lo stesso argomento come i `OnPaint` metodo <xref:System.Windows.Forms.Control.OnPaintBackground%2A> non è un metodo di evento vera. È presente alcun `PaintBackground` eventi e <xref:System.Windows.Forms.Control.OnPaintBackground%2A> non richiama i delegati di eventi. Quando si esegue l'override di <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo, una classe derivata non è necessaria per richiamare il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo della relativa classe base.  
  
## <a name="gdi-basics"></a>Nozioni fondamentali su GDI+  
 Il <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare varie forme, ad esempio cerchi, triangoli, archi e sui puntini di sospensione, nonché i metodi per la visualizzazione di testo. Il <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi e relativi sottospazi dei nomi contiene classi che incapsulano elementi grafici, ad esempio forme (cerchi, rettangoli, archi e altri), i colori, tipi di carattere, pennelli e così via. Per altre informazioni sulle [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], vedere [usando classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md). Di base [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] sono descritti inoltre nel [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Geometria dell'area di disegno  
 Il <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo consente di specificare la regione rettangolare disponibile per il controllo sullo schermo dell'utente, mentre la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> specifica l'area che viene effettivamente disegnata. (Tenere presente che il disegno viene effettuato il <xref:System.Windows.Forms.Control.Paint> metodo di eventi che accetta un <xref:System.Windows.Forms.PaintEventArgs> istanza come argomento). Un controllo potrebbe essere necessario disegnare solo una parte dell'area disponibile, come nel caso di modifiche di visualizzazione del controllo quando una sezione di piccole dimensioni. In questi casi, gli sviluppatori di controlli devono calcolare il rettangolo effettivo per disegnare e che viene passato al <xref:System.Windows.Forms.Control.Invalidate%2A>. Le versioni di overload <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento utilizzano l'argomento per generare il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Frammento di codice seguente viene illustrato come il `FlashTrackBar` controllo personalizzato calcola l'area rettangolare da disegnare. Il `client` variabile denota il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà. Per un esempio completo, vedere [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberare le risorse grafiche  
 Gli oggetti di grafica sono costosi perché usano le risorse di sistema. Questi oggetti includono le istanze del <xref:System.Drawing.Graphics?displayProperty=nameWithType> nonché le istanze della classe <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>e altre classi di grafica. È importante che si crea una risorsa di grafica solo quando è necessario e lo rilascia appena si al termine dell'utilizzo. Se si crea un tipo che implementa il <xref:System.IDisposable> l'interfaccia, chiamare il <xref:System.IDisposable.Dispose%2A> metodo quando si è terminato di utilizzarlo per liberare risorse.  
  
 Frammento di codice seguente viene illustrato come la `FlashTrackBar` controllo personalizzato crea e rilascia un <xref:System.Drawing.Brush> risorsa. Per il codice sorgente completo, vedere [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Creare un controllo di Windows Form che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
