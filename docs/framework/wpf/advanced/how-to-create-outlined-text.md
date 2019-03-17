---
title: 'Procedura: Creare testo con contorni'
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
ms.openlocfilehash: 5de1068401dac61c5de5b86604da9417e18a94ae
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125941"
---
# <a name="how-to-create-outlined-text"></a>Procedura: Creare testo con contorni
Nella maggior parte dei casi, quando si aggiungono ornamento per le stringhe di testo di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] un'applicazione, si usa il testo in termini di una raccolta di caratteri discreti o glifi. Ad esempio, è possibile creare un pennello sfumato lineare e metterle in pratica per la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.TextBox> oggetto. Quando si visualizzano o si modifica la casella di testo, il pennello sfumato lineare viene applicato automaticamente al set corrente di caratteri nella stringa di testo.  
  
 ![Testo visualizzato con pennello sfumato lineare](./media/how-to-create-outlined-text/text-linear-gradient.jpg)    
  
 Tuttavia, è anche possibile convertire testo in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo visivamente accattivanti. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Quando il testo viene convertito in un <xref:System.Windows.Media.Geometry> dell'oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.  
  
 Gli esempi seguenti illustrano alcuni modi per creare effetti visivi modificando il tratto e riempimento del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 È anche possibile modificare il rettangolo delimitatore, o un'evidenziazione, del testo convertito. L'esempio seguente illustra un modo per creare effetti visivi modificando il tratto ed evidenziazione del testo convertito.  
  
 ![Testo con pennello immagine applicato per tracciare ed evidenziare](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Esempio  
 La chiave per la conversione del testo a un <xref:System.Windows.Media.Geometry> oggetto consiste nell'usare il <xref:System.Windows.Media.FormattedText> oggetto. Dopo aver creato questo oggetto, è possibile usare la <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> e <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> metodi per convertire il testo da <xref:System.Windows.Media.Geometry> oggetti. Il primo metodo restituisce la geometria del testo formattato; il secondo metodo restituisce che la geometria del testo formattato del rettangolo. Esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie di testo formattato e il relativo riquadro delimitatore.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Per visualizzare l'oggetto recuperato il <xref:System.Windows.Media.Geometry> oggetti, è necessario accedere il <xref:System.Windows.Media.DrawingContext> dell'oggetto che viene visualizzato il testo convertito. Questi esempi di codice, questa operazione viene eseguita tramite la creazione di un oggetto di controllo personalizzato che deriva da una classe che supporta il rendering definite dall'utente.  
  
 Per visualizzare <xref:System.Windows.Media.Geometry> oggetti nel controllo personalizzato, specificare una sostituzione per il <xref:System.Windows.UIElement.OnRender%2A> (metodo). Deve usare il metodo sottoposto a override il <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> metodo consente di disegnare la <xref:System.Windows.Media.Geometry> oggetti.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Per l'origine dell'oggetto di controllo utente personalizzato di esempio, vedere [OutlineTextControl.cs per C# ](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) e [OutlineTextControl.vb per Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb). 
  
## <a name="see-also"></a>Vedere anche
- [Disegno di testo formattato](drawing-formatted-text.md)
