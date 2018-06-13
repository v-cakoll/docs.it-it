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
ms.openlocfilehash: a2d7a02e725e3f8065b80a6b30ea21158be43ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541388"
---
# <a name="rendering-a-windows-forms-control"></a>Rendering di un controllo Windows Form
Per il rendering si intende il processo di creazione di una rappresentazione visiva sullo schermo dell'utente. Windows Form utilizza [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (la nuova libreria grafica di Windows) per il rendering. Le classi gestite che forniscono accesso a [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] presenti il <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi e i relativi sottospazi dei nomi.  
  
 Gli elementi seguenti sono coinvolti nel rendering del controllo:  
  
-   La funzionalità di disegno fornite dalla classe di base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
-   Gli elementi essenziali del [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] libreria grafica.  
  
-   La geometria dell'area di disegno.  
  
-   La procedura di liberazione di risorse grafiche.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funzionalità di disegno fornite dal controllo  
 La classe di base <xref:System.Windows.Forms.Control> fornisce funzionalità di disegno tramite il relativo <xref:System.Windows.Forms.Control.Paint> evento. Genera un controllo di <xref:System.Windows.Forms.Control.Paint> evento ogni volta che è necessario aggiornare la relativa visualizzazione. Per ulteriori informazioni sugli eventi in .NET Framework, vedere [gestione e generazione di eventi](../../../../docs/standard/events/index.md).  
  
 Classe di dati dell'evento per il <xref:System.Windows.Forms.Control.Paint> evento, <xref:System.Windows.Forms.PaintEventArgs>, contiene i dati necessari per la creazione di un controllo, ovvero un handle a un oggetto grafico e un oggetto rettangolo che rappresenta l'area da disegnare in. Questi oggetti vengono visualizzati grassetto nel frammento di codice seguente.  
  
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
  
 <xref:System.Drawing.Graphics> è una classe gestita che incapsula le funzionalità di disegno, come descritto nella discussione di [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] più avanti in questo argomento. Il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> è un'istanza di <xref:System.Drawing.Rectangle> struttura e definisce l'area disponibile per il disegno di un controllo. Gli sviluppatori di controlli è possono calcolare il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> utilizzando il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di geometria più avanti in questo argomento.  
  
 Un controllo deve fornire la logica di rendering eseguendo l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo che eredita da <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> Ottiene l'accesso a un oggetto grafico e un rettangolo da disegnare tramite il <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> e il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà del <xref:System.Windows.Forms.PaintEventArgs> istanza passata a esso.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della base <xref:System.Windows.Forms.Control> classe non implementa alcuna funzionalità di disegno ma richiama semplicemente i delegati registrati con il <xref:System.Windows.Forms.Control.Paint> evento. Quando esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A>, in genere, è necessario richiamare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base in modo che i delegati registrati possano ricevere il <xref:System.Windows.Forms.Control.Paint> evento. Tuttavia, i controlli l'intera superficie di disegno non devono richiamare la classe base <xref:System.Windows.Forms.Control.OnPaint%2A>, in quanto si verificherebbe lo sfarfallio. Per un esempio di override di <xref:System.Windows.Forms.Control.OnPaint%2A> eventi, vedere il [procedura: creare un Windows Form controllo che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo; in alternativa, richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo (ereditato da <xref:System.Windows.Forms.Control>) o un altro metodo che richiama <xref:System.Windows.Forms.Control.Invalidate%2A>. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo richiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A>. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo viene sottoposto a overload e, in base agli argomenti forniti al <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un controllo viene ridisegnata alcuni o tutti i relativi area dello schermo.  
  
 La base <xref:System.Windows.Forms.Control> classe definisce un altro metodo è utile per il disegno, ovvero il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> Disegna lo sfondo (e in tal modo la forma) della finestra ed è garantito veloce, mentre il <xref:System.Windows.Forms.Control.OnPaint%2A> disegna i dettagli e potrebbero essere più lenti perché singole richieste di disegno vengono combinate in un unico <xref:System.Windows.Forms.Control.Paint> evento che copre tutte le aree che devono essere ridisegnato. È possibile richiamare il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si vuole disegnare uno sfondo con sfumature di colore per il controllo.  
  
 Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ha una nomenclatura simile a quello degli eventi e prende lo stesso argomento di `OnPaint` metodo <xref:System.Windows.Forms.Control.OnPaintBackground%2A> non è un metodo di evento true. Non esiste alcun `PaintBackground` evento e <xref:System.Windows.Forms.Control.OnPaintBackground%2A> non richiamare delegati dell'evento. Quando si esegue l'override di <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo, una classe derivata non è necessaria richiamare il <xref:System.Windows.Forms.Control.OnPaintBackground%2A> metodo della relativa classe base.  
  
## <a name="gdi-basics"></a>Nozioni fondamentali su GDI+  
 La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare forme diverse, ad esempio cerchi, triangoli, archi e puntini di sospensione, nonché i metodi per la visualizzazione di testo. Il <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi e i relativi sottospazi dei nomi contiene classi che incapsulano elementi grafici, quali forme (cerchi, rettangoli, archi e altri), colori, tipi di carattere, pennelli e così via. Per ulteriori informazioni su [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], vedere [utilizzando classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md). Gli aspetti principali di [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] sono descritti anche nel [procedura: creare un Windows Form controllo che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Geometria dell'area di disegno  
 Il <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo specifica l'area rettangolare disponibile per il controllo sullo schermo dell'utente, mentre il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà <xref:System.Windows.Forms.PaintEventArgs> specifica l'area effettivamente disegnata. (Tenere presente che è stato eseguito il disegno <xref:System.Windows.Forms.Control.Paint> metodo eventi che accetta un <xref:System.Windows.Forms.PaintEventArgs> istanza come argomento). Un controllo potrebbe essere necessario disegnare solo una parte dell'area disponibile, come nel caso di modifiche di visualizzazione del controllo quando una piccola sezione. In questi casi, gli sviluppatori di controlli devono calcolare il rettangolo effettivo per disegnare e passarlo a <xref:System.Windows.Forms.Control.Invalidate%2A>. Versioni di overload <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento utilizzano l'argomento per generare il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Frammento di codice riportato di seguito viene illustrato come la `FlashTrackBar` controllo personalizzato calcola l'area rettangolare da disegnare. Il `client` variabile denota il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà. Per un esempio completo, vedere [procedura: creare un Windows Form controllo che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberazione di risorse grafiche  
 Gli oggetti di grafica sono costosi in quanto l'utilizzo di risorse di sistema. Questi oggetti includono le istanze del <xref:System.Drawing.Graphics?displayProperty=nameWithType> classe nonché le istanze di <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>e altre classi di grafica. È importante creare una risorsa grafica solo quando è necessario e rilasciarlo appena si termina di utilizzarla. Se si crea un tipo che implementa il <xref:System.IDisposable> interfaccia, chiamare il relativo <xref:System.IDisposable.Dispose%2A> metodo quando si è terminato con esso per liberare risorse.  
  
 Frammento di codice riportato di seguito viene illustrato come la `FlashTrackBar` controllo personalizzato crea e rilascia un <xref:System.Drawing.Brush> risorse. Per il codice sorgente completo, vedere [procedura: creare un Windows Form controllo che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare un controllo di Windows Form che visualizzi lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
