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
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142433"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedura: creare oggetti Graphics per disegnare
Prima di poter disegnare linee e forme, eseguire il rendering del testo o <xref:System.Drawing.Graphics> visualizzare e modificare le immagini con GDI, è necessario creare un oggetto. L'oggetto <xref:System.Drawing.Graphics> rappresenta una superficie di disegno GDI, ed è l'oggetto utilizzato per creare immagini grafiche.  
  
 L'utilizzo della grafica prevede due passaggi:  
  
1. Creazione <xref:System.Drawing.Graphics> di un oggetto.  
  
2. Utilizzo <xref:System.Drawing.Graphics> dell'oggetto per disegnare linee e forme, eseguire il rendering del testo o visualizzare e manipolare le immagini.  
  
## <a name="creating-a-graphics-object"></a>Creazione di un oggetto GraphicsCreating a Graphics Object  
 Un oggetto grafico può essere creato in diversi modi.  
  
#### <a name="to-create-a-graphics-object"></a>Per creare un oggetto grafico  
  
- Ricevere un riferimento a un oggetto <xref:System.Windows.Forms.PaintEventArgs> grafico <xref:System.Windows.Forms.Control.Paint> come parte dell'evento di un form o di un controllo. In genere si ottiene un riferimento a un oggetto grafico durante la creazione di codice di disegno per un controllo. Analogamente, è anche possibile ottenere un <xref:System.Drawing.Printing.PrintPageEventArgs> oggetto grafico <xref:System.Drawing.Printing.PrintDocument.PrintPage> come <xref:System.Drawing.Printing.PrintDocument>proprietà dell'oggetto quando si gestisce l'evento per un oggetto .  
  
     -oppure-  
  
- Chiamare <xref:System.Windows.Forms.Control.CreateGraphics%2A> il metodo di un controllo o <xref:System.Drawing.Graphics> di un form per ottenere un riferimento a un oggetto che rappresenta la superficie di disegno di tale controllo o form. Utilizzare questo metodo se si desidera disegnare su un form o un controllo già esistente.  
  
     -oppure-  
  
- Creare <xref:System.Drawing.Graphics> un oggetto da qualsiasi <xref:System.Drawing.Image>oggetto che eredita da . Questo approccio è utile quando si desidera modificare un'immagine già esistente.  
  
     Nelle sezioni seguenti vengono fornite informazioni dettagliate su ognuno di questi processi.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs nel gestore eventi Paint  
 Durante la <xref:System.Windows.Forms.PaintEventHandler> programmazione <xref:System.Drawing.Printing.PrintDocument.PrintPage> di <xref:System.Drawing.Printing.PrintDocument>controlli for o for a , <xref:System.Windows.Forms.PaintEventArgs> viene <xref:System.Drawing.Printing.PrintPageEventArgs>fornito un oggetto grafico come una delle proprietà di o .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Per ottenere un riferimento a un Graphics oggetto dal PaintEventArgs nel Paint evento  
  
1. Dichiarare <xref:System.Drawing.Graphics> l'oggetto.  
  
2. Assegnare la variabile <xref:System.Drawing.Graphics> per fare riferimento <xref:System.Windows.Forms.PaintEventArgs>all'oggetto passato come parte dell'oggetto .  
  
3. Inserire codice per disegnare il form o il controllo.  
  
     L'esempio seguente mostra <xref:System.Drawing.Graphics> come fare <xref:System.Windows.Forms.PaintEventArgs> riferimento <xref:System.Windows.Forms.Control.Paint> a un oggetto da nell'evento:  
  
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
 È inoltre possibile <xref:System.Windows.Forms.Control.CreateGraphics%2A> utilizzare il metodo di un controllo <xref:System.Drawing.Graphics> o di una maschera per ottenere un riferimento a un oggetto che rappresenta la superficie di disegno di tale controllo o form.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Per creare un graphics oggetto con il CreateGraphics metodo  
  
- Chiamare <xref:System.Windows.Forms.Control.CreateGraphics%2A> il metodo del form o del controllo su cui si desidera eseguire il rendering della grafica.  
  
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
  
## <a name="create-from-an-image-object"></a>Creazione da un oggetto immagine  
 Inoltre, è possibile creare un oggetto grafico da <xref:System.Drawing.Image> qualsiasi oggetto che deriva dalla classe .  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Per creare un Graphics oggetto da un Image  
  
- Chiamare <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> il metodo , specificando il nome della variabile Image <xref:System.Drawing.Graphics> da cui si desidera creare un oggetto.  
  
     Nell'esempio seguente viene <xref:System.Drawing.Bitmap> illustrato come utilizzare un oggetto:The following example shows how to use a object:  
  
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
> È possibile <xref:System.Drawing.Graphics> creare oggetti solo da file bmp non indicizzati, ad esempio file bmp a 16 bit, a 24 bit e a 32 bit. Ogni pixel dei file .bmp non indicizzati contiene un colore, a differenza dei pixel dei file .bmp indicizzati, che contengono un indice di una tabella dei colori.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Disegno e manipolazione di forme e immagini  
 Dopo la creazione, <xref:System.Drawing.Graphics> un oggetto può essere utilizzato per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini. Gli oggetti principali utilizzati <xref:System.Drawing.Graphics> con l'oggetto sono:  
  
- La <xref:System.Drawing.Pen> classe: utilizzata per disegnare linee, delineare forme o eseguire il rendering di altre rappresentazioni geometriche.  
  
- Classe: <xref:System.Drawing.Brush> utilizzata per riempire aree di grafica, ad esempio forme, immagini o testo riempiti.  
  
- La <xref:System.Drawing.Font> classe: fornisce una descrizione delle forme da utilizzare per il rendering del testo.  
  
- Struttura: <xref:System.Drawing.Color> rappresenta i diversi colori da visualizzare.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Per utilizzare l'oggetto Graphics creato  
  
- Lavora con l'oggetto appropriato elencato sopra per disegnare ciò di cui hai bisogno.  
  
     Per altre informazioni, vedere gli argomenti seguenti:  
  
    |Per eseguire il rendering|Vedere|  
    |---------------|---------|  
    |Linee|[Procedura: disegnare una linea in un Windows Form](how-to-draw-a-line-on-a-windows-form.md)|  
    |Forme|[Procedura: creare una forma con contorno](how-to-draw-an-outlined-shape.md)|  
    |Text|[Procedura: disegnare testo in un Windows Form](how-to-draw-text-on-a-windows-form.md)|  
    |Immagini|[Procedura: Eseguire il rendering delle immagini con GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Eseguire il rendering delle immagini con GDI+](how-to-render-images-with-gdi.md)
