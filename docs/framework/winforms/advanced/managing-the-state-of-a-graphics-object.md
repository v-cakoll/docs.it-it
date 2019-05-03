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
ms.openlocfilehash: 8fc92bf84def50bed54a054ae634a8a08c8835c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936878"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Gestione dello stato di un oggetto Graphics
Il <xref:System.Drawing.Graphics> classe è il fulcro di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Per disegnare qualsiasi elemento, per ottenere un <xref:System.Drawing.Graphics> dell'oggetto, impostarne le proprietà e chiamarne i metodi <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>e così via).  
  
 L'esempio seguente chiama il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo di un <xref:System.Drawing.Graphics> oggetto. Il primo argomento passato per il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo è un <xref:System.Drawing.Pen> oggetto.  
  
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
 Oggetto <xref:System.Drawing.Graphics> oggetto fornire più metodi di disegno, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A> e <xref:System.Drawing.Graphics.DrawRectangle%2A>. Oggetto <xref:System.Drawing.Graphics> viene conservato anche lo stato di grafica, che può essere suddivisi nelle categorie seguenti:  
  
- Impostazioni relative alla qualità  
  
- Trasformazioni  
  
- Area di ritaglio  
  
### <a name="quality-settings"></a>Impostazioni relative alla qualità  
 Oggetto <xref:System.Drawing.Graphics> oggetto presenta varie proprietà che determinano la qualità degli elementi da cui vengono disegnati. Ad esempio, è possibile impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà per specificare il tipo di anti-aliasing (se presente) applicato al testo. Altre proprietà che influiscono sulla qualità sono <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, e <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 L'esempio seguente disegna due ellissi, uno con la modalità di attenuazione impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> e uno con la modalità di attenuazione impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
 Oggetto <xref:System.Drawing.Graphics> oggetto mantiene due trasformazioni (pagina e world) che vengono applicate a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto. Tutte le trasformazioni affini possono essere archiviate nella trasformazione globale. Trasformazioni affini includono scalabilità, ruotare, riflettere, inclinare e la conversione. La trasformazione della pagina utilizzabile per la scalabilità e per la modifica delle unità (ad esempio, in pixel su pollici). Per altre informazioni, vedere [sistemi di Coordinate e trasformazioni](coordinate-systems-and-transformations.md).  
  
 L'esempio seguente imposta le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> oggetto. La trasformazione globale è impostata su una rotazione di 30 gradi. La trasformazione della pagina viene impostata in modo che le coordinate passate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> verrà considerata come millimetri invece di pixel. Il codice effettua due chiamate identiche al <xref:System.Drawing.Graphics.DrawEllipse%2A> (metodo). La trasformazione globale viene applicata al primo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata ed entrambe le trasformazioni (pagina e world) vengono applicate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamare.  
  
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
  
 La figura seguente mostra due ellissi. Si noti che la rotazione di 30 gradi intorno all'origine del sistema di coordinate (nell'angolo superiore sinistro dell'area client), non rispetto al centro dei puntini di sospensione. Si noti inoltre che la larghezza della penna di 1 significa 1 pixel per la prima ellisse e a 1 millimetro della seconda ellisse.  
  
 ![Figura che mostra due ellissi: larghezza di rotazione e penna.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Area di ritaglio  
 Oggetto <xref:System.Drawing.Graphics> oggetto mantiene un'area di ridimensionamento che si applica a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto. È possibile impostare l'area di visualizzazione chiamando il <xref:System.Drawing.Graphics.SetClip%2A> (metodo).  
  
 L'esempio seguente crea un'area a forma di segno più per formare l'unione di due rettangoli. Tale area viene designata come area di visualizzazione di un <xref:System.Drawing.Graphics> oggetto. Quindi il codice disegna due righe che sono limitate all'interno dell'area di visualizzazione.  
  
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
  
 La figura seguente illustra le linee tagliate:  
  
 ![Diagramma che mostra l'area di ritaglio limitata.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di contenitori di grafica annidati](using-nested-graphics-containers.md)
