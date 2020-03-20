---
title: 'Procedura: creare testo con contorni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186863"
---
# <a name="how-to-create-outlined-text"></a>Procedura: creare testo con contorni
Nella maggior parte dei casi, quando si [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aggiungono ornamenti alle stringhe di testo nell'applicazione, si utilizza il testo in termini di una raccolta di caratteri discreti o glifi. Ad esempio, è possibile creare un pennello <xref:System.Windows.Controls.Control.Foreground%2A> sfumato lineare e applicarlo alla proprietà di un <xref:System.Windows.Controls.TextBox> oggetto. Quando si visualizza o si modifica la casella di testo, il pennello sfumato lineare viene applicato automaticamente al set di caratteri corrente nella stringa di testo.  
  
 ![Testo visualizzato con pennello sfumato lineare](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 Tuttavia, è anche <xref:System.Windows.Media.Geometry> possibile convertire il testo in oggetti, consentendo di creare altri tipi di testo ricco di immagini. Ad esempio, è <xref:System.Windows.Media.Geometry> possibile creare un oggetto in base al contorno di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Quando il testo <xref:System.Windows.Media.Geometry> viene convertito in un oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.  
  
 Gli esempi seguenti illustrano diversi modi per creare effetti visivi modificando la traccia e il riempimento del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 È anche possibile modificare il rettangolo del riquadro di delimitazione, o evidenziare, del testo convertito. Nell'esempio seguente viene illustrato un modo per creare effetti visivi modificando il tratto e l'evidenziazione del testo convertito.  
  
 ![Testo con pennello immagine applicato al tratto e all'evidenziazione](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Esempio  
 La chiave per convertire <xref:System.Windows.Media.Geometry> il testo in <xref:System.Windows.Media.FormattedText> un oggetto consiste nell'utilizzare l'oggetto. Dopo aver creato questo oggetto, <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> è <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> possibile utilizzare i <xref:System.Windows.Media.Geometry> metodi e per convertire il testo in oggetti. Il primo metodo restituisce la geometria del testo formattato; il secondo metodo restituisce la geometria del riquadro di delimitazione del testo formattato. Nell'esempio di codice riportato di seguito viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie del testo formattato e del relativo riquadro di delimitazione.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Per visualizzare gli <xref:System.Windows.Media.Geometry> oggetti recuperati, è necessario <xref:System.Windows.Media.DrawingContext> accedere all'oggetto che visualizza il testo convertito. In questi esempi di codice, questa operazione viene eseguita creando un oggetto controllo personalizzato derivato da una classe che supporta il rendering definito dall'utente.  
  
 Per <xref:System.Windows.Media.Geometry> visualizzare gli oggetti nel controllo personalizzato, fornire un override per il <xref:System.Windows.UIElement.OnRender%2A> metodo. Il metodo sottoposto <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> a override <xref:System.Windows.Media.Geometry> deve utilizzare il metodo per disegnare gli oggetti.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Per l'origine dell'oggetto controllo utente personalizzato di esempio, vedere [OutlineTextControl.cs per C'](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) e [OutlineTextControl.vb per Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).
  
## <a name="see-also"></a>Vedere anche

- [Disegno di testo formattato](drawing-formatted-text.md)
