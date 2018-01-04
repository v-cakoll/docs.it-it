---
title: Gestione dello stato di un oggetto Graphics
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a9514d845580bfe921fefa5f4a249c5a905d03d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="managing-the-state-of-a-graphics-object"></a>Gestione dello stato di un oggetto Graphics
Il <xref:System.Drawing.Graphics> classe è il fulcro di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Per creare qualsiasi oggetto, per ottenere un <xref:System.Drawing.Graphics> dell'oggetto, impostarne le proprietà e chiamarne i metodi <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>e così via).  
  
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
 Oggetto <xref:System.Drawing.Graphics> oggetto forniscono più metodi di disegno, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A> e <xref:System.Drawing.Graphics.DrawRectangle%2A>. Oggetto <xref:System.Drawing.Graphics> viene conservato anche lo stato di grafica, che può essere suddivisi nelle categorie seguenti:  
  
-   Impostazioni di qualità  
  
-   Trasformazioni  
  
-   Area di visualizzazione  
  
### <a name="quality-settings"></a>Impostazioni di qualità  
 Oggetto <xref:System.Drawing.Graphics> oggetto ha diverse proprietà che determinano la qualità degli elementi da cui vengono disegnate. Ad esempio, è possibile impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà per specificare il tipo di anti-aliasing (se presente) applicato al testo. Le altre proprietà che influiscono sulla qualità sono <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, e <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 Nell'esempio seguente disegna due ellissi, una con la stessa modalità impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> e uno con la stessa modalità impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
 Oggetto <xref:System.Drawing.Graphics> oggetto gestisce due trasformazioni (globali e pagina) che vengono applicate a tutti gli elementi che disegnati <xref:System.Drawing.Graphics> oggetto. Qualsiasi trasformazione affine può essere archiviati nella trasformazione globale. Trasformazioni affini includono la scalabilità, ruotare, riflettere, inclinazione e la conversione. La trasformazione della pagina utilizzabile per la scalabilità e per la modifica di unità (ad esempio, in pixel per pollici). Per ulteriori informazioni, vedere [sistemi di Coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 Nell'esempio seguente imposta le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> oggetto. La trasformazione globale è impostata su una rotazione di 30 gradi. La trasformazione di pagina viene impostata in modo che le coordinate passate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> verrà considerato come millimetri anziché pixel. Il codice richiama due identici per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo. La trasformazione globale viene applicata al primo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata ed entrambe le trasformazioni, world e pagina, vengono applicate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamare.  
  
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
  
 Nella figura seguente mostra due ellissi. Si noti che il 30 gradi di rotazione intorno all'origine del sistema di coordinate (angolo superiore sinistro dell'area client), non rispetto al centro dei puntini di sospensione. Si noti inoltre che la larghezza della penna di 1 significa 1 pixel per la prima ellisse e 1 millimetro della seconda ellisse.  
  
 ![Ovali](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>Area di visualizzazione  
 Oggetto <xref:System.Drawing.Graphics> oggetto mantiene un'area di visualizzazione che si applica a tutti gli elementi che disegnati <xref:System.Drawing.Graphics> oggetto. È possibile impostare l'area di visualizzazione chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.  
  
 L'esempio seguente crea un'area a forma di segno più tramite l'unione di due rettangoli. Tale area è designata come area di visualizzazione di un <xref:System.Drawing.Graphics> oggetto. Il codice crea quindi due righe che sono limitate all'interno dell'area di visualizzazione.  
  
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
  
 Nella figura seguente mostra le righe ritagliate.  
  
 ![Area di ritaglio limitata](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Uso di contenitori di grafica annidati](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
