---
title: Utilizzo di tipi di carattere e testo
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703368"
---
# <a name="using-fonts-and-text"></a>Utilizzo di tipi di carattere e testo
Sono disponibili diverse classi offerte dal [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per disegnare il testo in Windows Form. Il [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> classe dispone di numerose <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare diverse caratteristiche del testo, ad esempio percorso, rettangolo, tipo di carattere e il formato di delimitazione. Inoltre, è possibile disegnare e misurare il testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] usando il metodo statico <xref:System.Windows.Forms.TextRenderer.DrawText%2A> e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> metodi offerti dal `TextRenderer` classe. Il [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] metodi consentono anche di specificare posizione, tipo di carattere e il formato. È possibile scegliere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oppure [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per il rendering del testo; tuttavia, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] in genere offre migliori prestazioni e la misurazione del testo più accurate. Le altre classi che contribuiscono al rendering del testo `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, e `TextFormatFlags`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Costruire i tipi di carattere e famiglie di caratteri](how-to-construct-font-families-and-fonts.md)  
 Viene illustrato come creare `Font` e `FontFamily` oggetti.  
  
 [Procedura: Disegnare testo in una posizione specificata](how-to-draw-text-at-a-specified-location.md)  
 Descrive come disegnare testo in una determinata posizione utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Procedura: Disegnare testo sottoposto a wrapping in un rettangolo](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Illustra come disegnare il testo in un rettangolo utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md)  
 Viene illustrato come utilizzare [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per disegnare il testo.  
  
 [Procedura: Allineare il testo creato](how-to-align-drawn-text.md)  
 Viene illustrato come formattare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] testo.  
  
 [Procedura: Creare testo verticale](how-to-create-vertical-text.md)  
 Viene descritto come disegnare il testo allineato in senso verticale con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Procedura: Impostare punti di tabulazione nel testo disegnato](how-to-set-tab-stops-in-drawn-text.md)  
 Viene illustrato come disegnare il testo con le tabulazioni con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Procedura: Enumerare i tipi di carattere installati](how-to-enumerate-installed-fonts.md)  
 Viene illustrato come elencare i nomi dei tipi di carattere installati.  
  
 [Procedura: Creare una raccolta di caratteri privata](how-to-create-a-private-font-collection.md)  
 Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 [Procedura: Ottenere le metriche del tipo di carattere](how-to-obtain-font-metrics.md)  
 Viene illustrato come ottenere le metriche del tipo di carattere, ad esempio ascent di cella e dei valori descent con.  
  
 [Procedura: Usare l'antialiasing nel testo](how-to-use-antialiasing-with-text.md)  
 Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing.Font>  
 Descrive la classe e contiene collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.FontFamily>  
 Descrive la classe e contiene collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Descrive la classe e contiene collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Descrive la classe e contiene collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Descrive la classe e contiene collegamenti a tutti i relativi membri.
