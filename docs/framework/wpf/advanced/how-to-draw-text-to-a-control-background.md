---
title: 'Procedura: Disegnare testo sullo sfondo di un controllo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0c98422e337678e68a8e4b72979635e8c867b4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>Procedura: Disegnare testo sullo sfondo di un controllo
È possibile creare testo direttamente sullo sfondo di un controllo mediante la conversione di una stringa di testo a un <xref:System.Windows.Media.FormattedText> dell'oggetto e di disegno dell'oggetto per il controllo <xref:System.Windows.Media.DrawingContext>. È inoltre possibile utilizzare questa tecnica per disegnare sullo sfondo di oggetti derivati da <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.StackPanel>.  
  
 ![I controlli che visualizzano testo come sfondo](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Esempio di controlli con sfondi di testo personalizzati  
  
## <a name="example"></a>Esempio  
 Per disegnare lo sfondo di un controllo, creare un nuovo <xref:System.Windows.Media.DrawingBrush> dell'oggetto e disegnare il testo convertito nell'oggetto <xref:System.Windows.Media.DrawingContext>. Quindi, assegnare alla nuova <xref:System.Windows.Media.DrawingBrush> alla proprietà dello sfondo del controllo.  
  
 Esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> dell'oggetto e disegnare lo sfondo di un <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Button> oggetto.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.FormattedText>  
 [Disegno di testo formattato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
