---
title: Gestione dello stato di un oggetto Graphics
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182460"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Gestione dello stato di un oggetto Graphics
La <xref:System.Drawing.Graphics> classe si trova nel cuore di GDI. Per disegnare qualsiasi elemento, si ottiene <xref:System.Drawing.Graphics> un oggetto, <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>impostarne le proprietà e chiamarne i metodi , <xref:System.Drawing.Graphics.DrawString%2A>, e simili).  
  
 Nell'esempio seguente <xref:System.Drawing.Graphics.DrawRectangle%2A> viene <xref:System.Drawing.Graphics> chiamato il metodo di un oggetto . Il primo argomento <xref:System.Drawing.Graphics.DrawRectangle%2A> passato al <xref:System.Drawing.Pen> metodo è un oggetto.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>Stato grafica  
 Un <xref:System.Drawing.Graphics> oggetto non fornisce più che <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A>fornire metodi di disegno, ad esempio e . Un <xref:System.Drawing.Graphics> oggetto mantiene anche lo stato grafico, che può essere suddiviso nelle seguenti categorie:  
  
- Impostazioni di qualità  
  
- Trasformazioni  
  
- Area di ritaglio  
  
### <a name="quality-settings"></a>Impostazioni di qualità  
 Un <xref:System.Drawing.Graphics> oggetto dispone di diverse proprietà che influenzano la qualità degli elementi disegnati. Ad esempio, è <xref:System.Drawing.Graphics.TextRenderingHint%2A> possibile impostare la proprietà per specificare il tipo di antialiasing (se presente) applicato al testo. Altre proprietà che <xref:System.Drawing.Graphics.SmoothingMode%2A>influenzano <xref:System.Drawing.Graphics.CompositingQuality%2A>la <xref:System.Drawing.Graphics.InterpolationMode%2A>qualità sono , <xref:System.Drawing.Graphics.CompositingMode%2A>, , e .  
  
 L'esempio seguente disegna due ellissi, <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> una con la modalità <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>di arrotondamento impostata su e una con la modalità di arrotondamento impostata su :  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>Trasformazioni  
 Un <xref:System.Drawing.Graphics> oggetto mantiene due trasformazioni (mondo e pagina) che <xref:System.Drawing.Graphics> vengono applicate a tutti gli elementi disegnati da tale oggetto. Qualsiasi trasformazione affine può essere archiviata nella trasformazione globale. Le trasformazioni affini includono il ridimensionamento, la rotazione, la riflessione, l'inclinazione e la traslazione. La trasformazione di pagina può essere utilizzata per il ridimensionamento e per la modifica delle unità (ad esempio, da pixel a pollici). Per ulteriori informazioni, consultate [Sistemi di coordinate e trasformazioni.](coordinate-systems-and-transformations.md)  
  
 L'esempio seguente imposta le trasformazioni <xref:System.Drawing.Graphics> del mondo e della pagina di un oggetto. La trasformazione globale è impostata su una rotazione di 30 gradi. La trasformazione di pagina viene impostata <xref:System.Drawing.Graphics.DrawEllipse%2A> in modo che le coordinate passate alla seconda vengano considerate come millimetri anziché pixel. Il codice effettua due <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamate identiche al metodo. La trasformazione globale viene <xref:System.Drawing.Graphics.DrawEllipse%2A> applicata alla prima chiamata e entrambe le <xref:System.Drawing.Graphics.DrawEllipse%2A> trasformazioni (mondo e pagina) vengono applicate alla seconda chiamata.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 Nella figura seguente vengono illustrate le due ellissi. Si noti che la rotazione di 30 gradi è circa l'origine del sistema di coordinate (angolo superiore sinistro dell'area client) non intorno ai centri delle ellissi. Si noti inoltre che la larghezza della penna di 1 indica 1 pixel per la prima ellisse e 1 millimetro per la seconda ellisse.  
  
 ![Illustrazione che mostra due ellissi: rotazione e larghezza della penna.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Regione di ritaglio  
 Un <xref:System.Drawing.Graphics> oggetto mantiene un'area di ritaglio che <xref:System.Drawing.Graphics> si applica a tutti gli elementi disegnati da tale oggetto. È possibile impostare l'area <xref:System.Drawing.Graphics.SetClip%2A> di ritaglio chiamando il metodo .  
  
 Nell'esempio seguente viene creata un'area a forma di segno di più formando l'unione di due rettangoli. Tale area viene designata come <xref:System.Drawing.Graphics> area di ritaglio di un oggetto. Quindi il codice disegna due righe che sono limitate all'interno dell'area di ritaglio.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 La figura seguente mostra le linee ritagliate:  
  
 ![Diagramma che mostra l'area di ritaglio limitata.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di contenitori di grafica annidati](using-nested-graphics-containers.md)
