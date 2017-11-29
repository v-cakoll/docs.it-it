---
title: 'Procedura: creare testo con contorni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76d0dcf63f9d8a66106f4bcdc52a2bf98c75cdc4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-outlined-text"></a>Procedura: creare testo con contorni
Nella maggior parte dei casi, quando si aggiungono ornamenti per le stringhe di testo il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] un'applicazione, si utilizza il testo un insieme di caratteri discreti, o icone. Ad esempio, è possibile creare un pennello sfumato lineare e applicarlo al <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.TextBox> oggetto. Quando si visualizzano o si modifica la casella di testo, il pennello sfumato lineare viene applicato automaticamente al set di caratteri nella stringa di testo corrente.  
  
 ![Testo visualizzato con pennello sfumato lineare](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Esempio di un pennello sfumato lineare applicato a una casella di testo  
  
 Tuttavia, è anche possibile convertire il testo in <xref:System.Windows.Media.Geometry> oggetti, che consente di creare altri tipi di testo RTF visivamente. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Esempio di un pennello sfumato lineare applicato alla geometria della struttura del testo  
  
 Quando il testo viene convertito in un <xref:System.Windows.Media.Geometry> dell'oggetto, non è più un insieme di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.  
  
 Gli esempi seguenti illustrano alcuni modi per creare effetti visivi modificando il tratto e riempimento del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Esempio di impostazione di tratto e riempimento in colori diversi  
  
 ![Testo con tratto con immagine applicato alla traccia](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Esempio di un pennello immagine applicato al tratto  
  
 È inoltre possibile modificare il rettangolo delimitatore o evidenziazione, del testo convertito. Nell'esempio seguente viene illustrata una modalità di creazione di effetti visivi modificando il tratto e l'evidenziazione del testo convertito.  
  
 ![Testo con tratto con immagine applicato alla traccia](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Esempio di un pennello immagine applicato al tratto ed evidenziazione  
  
## <a name="example"></a>Esempio  
 La chiave per la conversione del testo per un <xref:System.Windows.Media.Geometry> oggetto consiste nell'utilizzare il <xref:System.Windows.Media.FormattedText> oggetto. Dopo aver creato questo oggetto, è possibile utilizzare il <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> e <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> metodi per convertire il testo da <xref:System.Windows.Media.Geometry> oggetti. Il primo metodo restituisce la geometria di testo formattato. il secondo metodo restituisce che la geometria del testo formattato del rettangolo di selezione. Esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie del testo formattato e il rettangolo di selezione.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Per visualizzare l'oggetto recuperato il <xref:System.Windows.Media.Geometry> oggetti, è necessario accedere il <xref:System.Windows.Media.DrawingContext> dell'oggetto che viene visualizzato il testo convertito. Questi esempi di codice, questa operazione viene eseguita tramite la creazione di un oggetto di controllo personalizzato derivato da una classe che supporta il rendering definito dall'utente.  
  
 Per visualizzare <xref:System.Windows.Media.Geometry> oggetti nel controllo personalizzato, fornire un override per il <xref:System.Windows.UIElement.OnRender%2A> metodo. Deve utilizzare il metodo sottoposto a override di <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> metodo consente di disegnare il <xref:System.Windows.Media.Geometry> oggetti.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>Vedere anche  
 [Disegno di testo formattato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
