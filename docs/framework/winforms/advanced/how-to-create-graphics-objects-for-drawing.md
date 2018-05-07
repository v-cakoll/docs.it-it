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
ms.openlocfilehash: 3c25ddcfb3a566055afd5e233c2a69b3b7a8c66e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedura: creare oggetti Graphics per disegnare
Prima di poter creare linee e forme, il rendering del testo, visualizzare e modificare immagini con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario creare un <xref:System.Drawing.Graphics> oggetto. Il <xref:System.Drawing.Graphics> oggetto rappresenta un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie di disegno ed è l'oggetto che viene utilizzato per creare immagini grafiche.  
  
 Durante l'utilizzo di grafici sono disponibili due passaggi:  
  
1.  Creazione di un <xref:System.Drawing.Graphics> oggetto.  
  
2.  Utilizzo di <xref:System.Drawing.Graphics> oggetto disegnare linee e forme, il rendering del testo, o visualizzare e modificare immagini.  
  
## <a name="creating-a-graphics-object"></a>Creazione di un oggetto Graphics  
 Può creare un oggetto graphics in diversi modi.  
  
#### <a name="to-create-a-graphics-object"></a>Per creare un oggetto graphics  
  
-   Ricevere un riferimento a un oggetto grafico come parte di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> evento di un form o controllo. Si tratta in genere come ottenere un riferimento a un oggetto grafico durante la creazione di codice di disegno di un controllo. Analogamente, è possibile ottenere un oggetto graphics come proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestisce il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un <xref:System.Drawing.Printing.PrintDocument>.  
  
     oppure  
  
-   Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta l'area di disegno di tale controllo o un form. Utilizzare questo metodo se si desidera disegnare su un form o controllo che esiste già.  
  
     oppure  
  
-   Creare un <xref:System.Drawing.Graphics> oggetto da qualsiasi oggetto che eredita da <xref:System.Drawing.Image>. Questo approccio è utile quando si desidera modificare un'immagine già esistente.  
  
     Le sezioni seguenti forniscono informazioni dettagliate su ciascuno di questi processi.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs nel gestore dell'evento Paint  
 Durante la programmazione di <xref:System.Windows.Forms.PaintEventHandler> per i controlli o <xref:System.Drawing.Printing.PrintDocument.PrintPage> per un <xref:System.Drawing.Printing.PrintDocument>, viene fornito un oggetto grafico come una delle proprietà di <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Per ottenere un riferimento a un oggetto Graphics da PaintEventArgs nell'evento di disegno  
  
1.  Dichiarare il <xref:System.Drawing.Graphics> oggetto.  
  
2.  Assegnare la variabile per fare riferimento al <xref:System.Drawing.Graphics> oggetto passato come parte di <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Inserire il codice per disegnare il form o controllo.  
  
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
 È inoltre possibile utilizzare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta l'area di disegno di tale controllo o un form.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Per creare un oggetto grafico con il metodo CreateGraphics  
  
-   Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o controllo su cui si desidera eseguire il rendering di grafica.  
  
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
  
## <a name="create-from-an-image-object"></a>Il nome di un oggetto Image  
 Inoltre, è possibile creare un oggetto graphics da qualsiasi oggetto che deriva dalla <xref:System.Drawing.Image> classe.  
  
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
>  È possibile creare solo <xref:System.Drawing.Graphics> oggetti dai file BMP non indicizzati, ad esempio file con estensione bmp a 16 bit, a 24 bit e a 32 bit. Ogni pixel del file con estensione BMP non indicizzata contiene un colore, a differenza di pixel del file BMP indicizzati che contengono un indice per una tabella a colori.  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Creazione e modifica di immagini e forme  
 Dopo averlo creato, un <xref:System.Drawing.Graphics> oggetto può essere utilizzato per disegnare linee e forme, il rendering del testo, o visualizzare e modificare immagini. Gli oggetti principali utilizzati con il <xref:System.Drawing.Graphics> oggetto sono:  
  
-   La <xref:System.Drawing.Pen> classe, utilizzati per disegno di linee, tracciare forme o per il rendering di altre rappresentazioni geometriche.  
  
-   La <xref:System.Drawing.Brush> classe, utilizzata per riempire le aree di grafica, ad esempio testo, immagini o forme piene.  
  
-   La <xref:System.Drawing.Font> classe, viene fornita una descrizione delle forme da utilizzare durante il rendering di testo.  
  
-   Il <xref:System.Drawing.Color> struttura, ovvero rappresenta i diversi colori da visualizzare.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Utilizzare l'oggetto di grafica che è stato creato  
  
-   Utilizzare l'oggetto appropriato elencata in precedenza per disegnare gli elementi necessari.  
  
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
