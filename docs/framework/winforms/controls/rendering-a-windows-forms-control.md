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
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968269"
---
# <a name="rendering-a-windows-forms-control"></a>Rendering di un controllo Windows Form
Il rendering si riferisce al processo di creazione di una rappresentazione visiva sullo schermo di un utente. Windows Forms utilizza GDI (la nuova libreria grafica di Windows) per il rendering. Le classi gestite che forniscono l'accesso a GDI si trovano <xref:System.Drawing?displayProperty=nameWithType> nello spazio dei nomi e nei relativi sottospazi dei nomi.  
  
 Per il rendering del controllo sono necessari gli elementi seguenti:  
  
- Funzionalità di disegno fornita dalla classe <xref:System.Windows.Forms.Control?displayProperty=nameWithType>base.  
  
- Elementi essenziali della libreria grafica GDI.  
  
- Geometria dell'area di disegno.  
  
- Procedura per liberare risorse grafiche.  
  
## <a name="drawing-functionality-provided-by-control"></a>Funzionalità di disegno fornita dal controllo  
 La classe <xref:System.Windows.Forms.Control> base fornisce la funzionalità di disegno <xref:System.Windows.Forms.Control.Paint> tramite il relativo evento. Un controllo genera l' <xref:System.Windows.Forms.Control.Paint> evento ogni volta che è necessario aggiornare la visualizzazione. Per ulteriori informazioni sugli eventi nel .NET Framework, vedere [gestione e generazione di eventi](../../../standard/events/index.md).  
  
 La classe di dati dell'evento <xref:System.Windows.Forms.Control.Paint> per l' <xref:System.Windows.Forms.PaintEventArgs>evento,, include i dati necessari per il disegno di un controllo, ovvero un handle per un oggetto Graphics e un oggetto Rectangle che rappresenta l'area in cui disegnare. Questi oggetti vengono visualizzati in grassetto nel frammento di codice seguente.  
  
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
  
 <xref:System.Drawing.Graphics>è una classe gestita che incapsula la funzionalità di disegno, come descritto nella discussione di GDI più avanti in questo argomento. È un'istanza <xref:System.Drawing.Rectangle> della struttura e definisce l'area disponibile in cui un controllo può essere disegnato. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Uno sviluppatore del controllo può calcolare <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> usando la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di un controllo, come descritto nella discussione di Geometry più avanti in questo argomento.  
  
 Un controllo deve fornire la logica di rendering eseguendo l' <xref:System.Windows.Forms.Control.OnPaint%2A> override del metodo da <xref:System.Windows.Forms.Control>cui eredita. <xref:System.Windows.Forms.Control.OnPaint%2A>Ottiene l'accesso a un oggetto Graphics e a un rettangolo da creare tramite <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> l'oggetto <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> e le proprietà <xref:System.Windows.Forms.PaintEventArgs> dell'istanza passata.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di <xref:System.Windows.Forms.Control> base non implementa alcuna funzionalità di disegno, ma richiama solo i delegati dell'evento registrati con <xref:System.Windows.Forms.Control.Paint> l'evento. Quando si esegue <xref:System.Windows.Forms.Control.OnPaint%2A>l'override di, è in <xref:System.Windows.Forms.Control.OnPaint%2A> genere necessario richiamare il metodo della classe base in modo che <xref:System.Windows.Forms.Control.Paint> i delegati registrati ricevano l'evento. Tuttavia, i controlli che disegnano l'intera superficie non devono richiamare la classe <xref:System.Windows.Forms.Control.OnPaint%2A>di base, in quanto introduce lo sfarfallio. Per un esempio di override <xref:System.Windows.Forms.Control.OnPaint%2A> dell'evento, [vedere Procedura: Creare un controllo Windows Forms che mostra lo](how-to-create-a-windows-forms-control-that-shows-progress.md)stato di avanzamento.  
  
> [!NOTE]
> Non richiamare <xref:System.Windows.Forms.Control.OnPaint%2A> direttamente dal controllo, bensì richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo (Ereditato da <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Control.Invalidate%2A>) o un altro metodo che richiama. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo<xref:System.Windows.Forms.Control.OnPaint%2A>richiama a sua volta. Il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo è sottoposto a overload e, a seconda degli argomenti forniti a <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, un controllo ridisegnato una o tutte le relative aree dello schermo.  
  
 La classe <xref:System.Windows.Forms.Control> base definisce un altro metodo utile per il disegno, ovvero <xref:System.Windows.Forms.Control.OnPaintBackground%2A> il metodo.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>Disegna lo sfondo (e quindi la forma) della finestra ed è garantito che sia veloce, mentre <xref:System.Windows.Forms.Control.OnPaint%2A> dipinge i dettagli e potrebbe essere più lento perché le singole richieste di disegno vengono combinate in un unico <xref:System.Windows.Forms.Control.Paint> evento che copre tutte le aree che devono essere ridisegnato. Potrebbe essere necessario richiamare l'oggetto <xref:System.Windows.Forms.Control.OnPaintBackground%2A> se, ad esempio, si desidera creare uno sfondo sfumato per il controllo.  
  
 Mentre <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ha una nomenclatura simile a un evento e accetta lo stesso argomento `OnPaint` del metodo <xref:System.Windows.Forms.Control.OnPaintBackground%2A> , non è un vero metodo di evento. Non è presente `PaintBackground` alcun evento <xref:System.Windows.Forms.Control.OnPaintBackground%2A> e non richiama i delegati dell'evento. Quando si esegue l' <xref:System.Windows.Forms.Control.OnPaintBackground%2A> override del metodo, non è necessaria una classe derivata per <xref:System.Windows.Forms.Control.OnPaintBackground%2A> richiamare il metodo della relativa classe di base.  
  
## <a name="gdi-basics"></a>Nozioni fondamentali su GDI+  
 La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare varie forme, ad esempio cerchi, triangoli, archi ed ellissi, nonché metodi per la visualizzazione di testo. Lo <xref:System.Drawing?displayProperty=nameWithType> spazio dei nomi e i relativi sottospazi dei nomi contengono classi che incapsulano elementi grafici come forme (cerchi, rettangoli, archi e altri), colori, tipi di carattere, pennelli e così via. Per ulteriori informazioni su GDI, vedere [utilizzo di classi grafiche gestite](../advanced/using-managed-graphics-classes.md). Le nozioni di base di GDI sono descritte [anche nella procedura: Creare un controllo Windows Forms che mostra lo](how-to-create-a-windows-forms-control-that-shows-progress.md)stato di avanzamento.  
  
## <a name="geometry-of-the-drawing-region"></a>Geometria dell'area di disegno  
 La <xref:System.Windows.Forms.Control.ClientRectangle%2A> proprietà di un controllo specifica l'area rettangolare disponibile per il controllo sullo schermo dell'utente, mentre la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> specifica l'area effettivamente disegnata. Tenere presente che il disegno viene eseguito nel <xref:System.Windows.Forms.Control.Paint> metodo dell'evento che accetta <xref:System.Windows.Forms.PaintEventArgs> un'istanza come argomento. Un controllo potrebbe dover disegnare solo una parte dell'area disponibile, come nel caso in cui una piccola sezione della visualizzazione del controllo cambia. In questi casi, uno sviluppatore di controlli deve calcolare il rettangolo effettivo da creare e passarlo a <xref:System.Windows.Forms.Control.Invalidate%2A>. Le versioni di overload di <xref:System.Windows.Forms.Control.Invalidate%2A> che accettano un oggetto <xref:System.Drawing.Rectangle> o <xref:System.Drawing.Region> come argomento usano tale argomento per generare la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Nel frammento di codice seguente viene `FlashTrackBar` illustrato il modo in cui il controllo personalizzato calcola l'area rettangolare in cui eseguire il progetto. La `client` variabile denota la <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> proprietà. Per un esempio completo, vedere [procedura: Creare un controllo Windows Forms che mostra lo](how-to-create-a-windows-forms-control-that-shows-progress.md)stato di avanzamento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Liberare risorse grafiche  
 Gli oggetti grafici sono costosi perché usano risorse di sistema. Tali oggetti includono le <xref:System.Drawing.Graphics?displayProperty=nameWithType> istanze della classe, nonché le istanze di <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>e altre classi grafiche. È importante creare una risorsa grafica solo quando è necessario e rilasciarla subito dopo averla usata. Se si crea un tipo che implementa l' <xref:System.IDisposable> interfaccia, chiamare il <xref:System.IDisposable.Dispose%2A> relativo metodo al termine dell'operazione per liberare risorse.  
  
 Nel frammento di codice seguente viene `FlashTrackBar` illustrato come il controllo personalizzato crea <xref:System.Drawing.Brush> e rilascia una risorsa. Per il codice sorgente completo, vedere [procedura: Creare un controllo Windows Forms che mostra lo](how-to-create-a-windows-forms-control-that-shows-progress.md)stato di avanzamento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un controllo Windows Forms che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md)
