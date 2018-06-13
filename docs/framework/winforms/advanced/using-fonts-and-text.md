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
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526263"
---
# <a name="using-fonts-and-text"></a>Utilizzo di tipi di carattere e testo
Sono disponibili diverse classi offerto da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per il disegno di testo in Windows Form. Il [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> classe dispone di numerosi <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare varie funzionalità di testo, ad esempio percorso, formato, carattere e rettangolo di delimitazione. Inoltre, è possibile disegnare e misurare il testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mediante il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> metodi offerti dalla `TextRenderer` classe. Il [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] metodi consentono anche di specificare il percorso, tipo di carattere e formato. È possibile scegliere una [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per il rendering del testo; tuttavia, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] in genere offre migliori prestazioni e la misurazione più accurata di testo. Le altre classi che contribuiscono al rendering del testo `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, e `TextFormatFlags`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare caratteri e gruppi di caratteri](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Viene illustrato come creare `Font` e `FontFamily` oggetti.  
  
 [Procedura: Creare testo in una posizione specificata](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Viene descritto come disegnare testo in una determinata posizione utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Procedura: Creare testo disposto su più righe in un rettangolo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Illustra come disegnare il testo in un rettangolo utilizzando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Viene illustrato come utilizzare [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] per il disegno di testo.  
  
 [Procedura: Allineare il testo creato](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Viene illustrato come formattare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] testo.  
  
 [Procedura: Creare testo verticale](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Viene descritto come disegnare il testo allineato verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Procedura: Impostare punti di tabulazione nel testo disegnato](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Viene illustrato come disegnare testo con tabulazioni con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Procedura: Enumerare i tipi di carattere installati](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Viene illustrato come elencare i nomi dei tipi di carattere installati.  
  
 [Procedura: Creare una raccolta di caratteri privata](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 [Procedura: Recuperare i criteri di misurazione dei caratteri](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Viene illustrato come ottenere la metrica di tipo di carattere, ad esempio ascent di cella e dei valori descent con.  
  
 [Procedura: Usare l'antialiasing nel testo](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
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
