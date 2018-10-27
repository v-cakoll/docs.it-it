---
title: 'Procedura: creare oggetti Graphics per disegnare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 54175e27ca46431299db369f67f02051ef08d0d2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185196"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedura: creare oggetti Graphics per disegnare
Prima di poter creare linee e forme, il rendering del testo, o visualizzare e manipolare immagini con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario creare un <xref:System.Drawing.Graphics> oggetto. Il <xref:System.Drawing.Graphics> oggetto rappresenta un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie di disegno ed è l'oggetto che viene usato per creare immagini grafiche.  
  
 Nell'utilizzo dei grafici sono disponibili due passaggi:  
  
1.  Creazione di un <xref:System.Drawing.Graphics> oggetto.  
  
2.  Uso di <xref:System.Drawing.Graphics> oggetto per tracciare linee e forme, il rendering del testo, o visualizzare e manipolare immagini.  
  
## <a name="creating-a-graphics-object"></a>Creazione di un oggetto Graphics  
 Un oggetto grafico può essere creato in diversi modi.  
  
#### <a name="to-create-a-graphics-object"></a>Per creare un oggetto graphics  
  
-   Riceve un riferimento a un oggetto grafico come parte del <xref:System.Windows.Forms.PaintEventArgs> nella <xref:System.Windows.Forms.Control.Paint> eventi di un form o controllo. Si tratta in genere come si ottiene un riferimento a un oggetto grafico durante la creazione di codice di disegno per un controllo. Allo stesso modo, è possibile ottenere un oggetto grafico come una proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestiscono le <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un <xref:System.Drawing.Printing.PrintDocument>.  
  
     oppure  
  
-   Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno di tale controllo o form. Usare questo metodo se si desidera disegnare su un form o controllo già esistente.  
  
     oppure  
  
-   Creare un <xref:System.Drawing.Graphics> oggetti da qualsiasi oggetto che eredita da <xref:System.Drawing.Image>. Questo approccio è utile quando si desidera modificare un'immagine già esistente.  
  
     Le sezioni seguenti forniscono informazioni dettagliate su ognuno di questi processi.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs nel gestore dell'evento Paint  
 Durante la programmazione di <xref:System.Windows.Forms.PaintEventHandler> per i controlli o il <xref:System.Drawing.Printing.PrintDocument.PrintPage> per un <xref:System.Drawing.Printing.PrintDocument>, un oggetto graphics viene fornito come una delle proprietà della <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Per ottenere un riferimento a un oggetto grafico da PaintEventArgs l'evento di disegno  
  
1.  Dichiarare il <xref:System.Drawing.Graphics> oggetto.  
  
2.  Assegnare la variabile per fare riferimento il <xref:System.Drawing.Graphics> oggetto passato come parte di <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Inserire codice per disegnare il form o controllo.  
  
     Nell'esempio seguente viene illustrato come fare riferimento a un <xref:System.Drawing.Graphics> dall'oggetto di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> evento:  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a>Metodo CreateGraphics  
 È anche possibile usare la <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno di tale controllo o form.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Per creare un oggetto Graphics con il metodo CreateGraphics  
  
-   Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o controllo su cui si desidera eseguire il rendering della grafica.  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a>La creazione di un oggetto immagine  
 Inoltre, è possibile creare un oggetto graphics da qualsiasi oggetto che deriva dal <xref:System.Drawing.Image> classe.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Per creare un oggetto Graphics da un'immagine  
  
-   Chiamare il <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> metodo, specificando il nome della variabile di immagine da cui si desidera creare un <xref:System.Drawing.Graphics> oggetto.  
  
     Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Drawing.Bitmap> oggetto:  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  È possibile creare solo <xref:System.Drawing.Graphics> oggetti dai file BMP non indicizzata, ad esempio i file con estensione bmp a 16, 24 bit e 32 bit. Ogni pixel del file con estensione BMP non indicizzata contiene un colore, a differenza dei pixel dei file BMP indicizzata che contengono un indice a una tabella dei colori.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Creazione e modifica di forme e immagini  
 Dopo averlo creato, un <xref:System.Drawing.Graphics> oggetto può essere utilizzato per disegnare linee e forme, il rendering del testo, o visualizzare e modificare le immagini. Gli oggetti principal che vengono usati con il <xref:System.Drawing.Graphics> oggetto sono:  
  
-   Il <xref:System.Drawing.Pen> classe, usato per tracciare linee, la struttura di forme o altre rappresentazioni geometriche di rendering.  
  
-   Il <xref:System.Drawing.Brush> classe, utilizzato per riempire le aree di grafica, ad esempio forme con riempimento, immagini o testo.  
  
-   Il <xref:System.Drawing.Font> classe, viene fornita una descrizione delle forme da utilizzare durante il rendering di testo.  
  
-   Il <xref:System.Drawing.Color> struttura, ovvero rappresenta i colori diversi per la visualizzazione.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Usare l'oggetto grafico è stato creato  
  
-   Funziona con l'oggetto appropriato elencato in precedenza per disegnare gli elementi necessari.  
  
     Per altre informazioni, vedere i seguenti argomenti:  
  
    |Per eseguire il rendering|Vedere|  
    |---------------|---------|  
    |Linee|[Procedura: Disegnare una linea in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Forme|[Procedura: Creare una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Testo|[Procedura: Disegnare testo in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Immagini|[Procedura: Eseguire il rendering delle immagini con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Eseguire il rendering delle immagini con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
