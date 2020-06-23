---
title: 'Procedura: creare oggetti Graphics per disegnare'
description: Informazioni su come creare un oggetto grafico necessario per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini con GDI+.
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
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903207"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedura: creare oggetti Graphics per disegnare
Prima di poter disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini con GDI+, è necessario creare un <xref:System.Drawing.Graphics> oggetto. L' <xref:System.Drawing.Graphics> oggetto rappresenta una superficie di disegno GDI+ e è l'oggetto utilizzato per creare immagini grafiche.  
  
 L'uso della grafica prevede due passaggi:  
  
1. Creazione di un <xref:System.Drawing.Graphics> oggetto.  
  
2. Utilizzo dell' <xref:System.Drawing.Graphics> oggetto per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.  
  
## <a name="creating-a-graphics-object"></a>Creazione di un oggetto Graphics  
 Un oggetto Graphics può essere creato in diversi modi.  
  
#### <a name="to-create-a-graphics-object"></a>Per creare un oggetto Graphics  
  
- Ricevere un riferimento a un oggetto Graphics come parte di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> caso di un form o di un controllo. Questo è in genere il modo in cui si ottiene un riferimento a un oggetto Graphics quando si crea il codice del disegno per un controllo. Analogamente, è anche possibile ottenere un oggetto Graphics come proprietà di <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestisce l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un oggetto <xref:System.Drawing.Printing.PrintDocument> .  
  
     -oppure-  
  
- Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno del controllo o del form. Utilizzare questo metodo se si desidera creare in un form o in un controllo già esistente.  
  
     -oppure-  
  
- Creare un <xref:System.Drawing.Graphics> oggetto da qualsiasi oggetto che eredita da <xref:System.Drawing.Image> . Questo approccio è utile quando si desidera modificare un'immagine già esistente.  
  
     Le sezioni seguenti forniscono informazioni dettagliate su ognuno di questi processi.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs nel gestore eventi Paint  
 Quando si programma <xref:System.Windows.Forms.PaintEventHandler> per i controlli o <xref:System.Drawing.Printing.PrintDocument.PrintPage> per un <xref:System.Drawing.Printing.PrintDocument> , un oggetto Graphics viene fornito come una delle proprietà di <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs> .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Per ottenere un riferimento a un oggetto Graphics da PaintEventArgs nell'evento Paint  
  
1. Dichiarare l' <xref:System.Drawing.Graphics> oggetto.  
  
2. Assegnare la variabile per fare riferimento all' <xref:System.Drawing.Graphics> oggetto passato come parte di <xref:System.Windows.Forms.PaintEventArgs> .  
  
3. Inserire il codice per disegnare il form o il controllo.  
  
     Nell'esempio seguente viene illustrato come fare riferimento a un <xref:System.Drawing.Graphics> oggetto da <xref:System.Windows.Forms.PaintEventArgs> nell' <xref:System.Windows.Forms.Control.Paint> evento:  
  
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
 È anche possibile usare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno del controllo o del form.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Per creare un oggetto Graphics con il metodo CreateGraphics  
  
- Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o del controllo su cui si desidera eseguire il rendering della grafica.  
  
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
  
## <a name="create-from-an-image-object"></a>Crea da un oggetto Image  
 Inoltre, è possibile creare un oggetto Graphics da qualsiasi oggetto derivato dalla <xref:System.Drawing.Image> classe.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Per creare un oggetto Graphics da un'immagine  
  
- Chiamare il <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> metodo, specificando il nome della variabile di immagine dalla quale si desidera creare un <xref:System.Drawing.Graphics> oggetto.  
  
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
> È possibile creare <xref:System.Drawing.Graphics> oggetti solo da file con estensione bmp non indicizzati, ad esempio file con estensione bmp a 16 bit, a 24 bit e a 32 bit. Ogni pixel di file con estensione bmp non indicizzati include un colore, a differenza dei pixel dei file con estensione BMP indicizzati, che contengono un indice in una tabella dei colori.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Creazione e modifica di forme e immagini  
 Una volta creato, un <xref:System.Drawing.Graphics> oggetto può essere usato per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini. Gli oggetti Principal utilizzati con l' <xref:System.Drawing.Graphics> oggetto sono:  
  
- La <xref:System.Drawing.Pen> classe, utilizzata per disegnare linee, strutturare forme o per il rendering di altre rappresentazioni geometriche.  
  
- <xref:System.Drawing.Brush>Classe, utilizzata per riempire aree di elementi grafici, ad esempio forme riempite, immagini o testo.  
  
- La <xref:System.Drawing.Font> classe-fornisce una descrizione delle forme da usare per il rendering del testo.  
  
- La <xref:System.Drawing.Color> struttura, che rappresenta i diversi colori da visualizzare.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Per utilizzare l'oggetto Graphics creato  
  
- Usare l'oggetto appropriato elencato sopra per creare gli elementi necessari.  
  
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
