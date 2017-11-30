---
title: 'Procedura: disegnare un''area con un pennello di sistema'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Procedura: disegnare un'area con un pennello di sistema
Il <xref:System.Windows.SystemColors> classe fornisce l'accesso a pennelli di sistema e colori, ad esempio <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, e <xref:System.Windows.SystemColors.DesktopBrush%2A>. Un pennello di sistema è un <xref:System.Windows.Media.SolidColorBrush> che disegna un'area con il colore di sistema specificato. Un pennello di sistema produce sempre un riempimento a tinta unita e non può essere usato per creare una sfumatura.  
  
 È possibile usare i pennelli di sistema come risorsa statica o dinamica. Usare una risorsa dinamica se si desidera che il pennello si aggiorni automaticamente in caso di modifica mentre l'applicazione è in esecuzione. In caso contrario, usare una risorsa statica. La classe SystemColors contiene un'ampia gamma di proprietà statiche che seguono una rigida convenzione di denominazione:  
  
-   *\<SystemColor>*Brush  
  
     Ottiene un riferimento statico a una <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
-   *\<SystemColor>*BrushKey  
  
     Ottiene un riferimento dinamico a un <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
-   *\<SystemColor>*Color  
  
     Ottiene un riferimento statico a una <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
-   *\<SystemColor>*ColorKey  
  
     Ottiene un riferimento dinamico per il <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
 Un colore di sistema è un <xref:System.Windows.Media.Color> struttura che può essere usato per configurare un pennello. Ad esempio, è possibile creare una sfumatura tramite colori di sistema impostando il <xref:System.Windows.Media.GradientStop.Color%2A> le proprietà di un <xref:System.Windows.Media.LinearGradientBrush> sfumatura dell'oggetto con colori di sistema. Per un esempio, vedere [Usa colori di sistema in una sfumatura](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un riferimento di pennello di sistema dinamico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 L'esempio seguente usa un riferimento di pennello di sistema statico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Per un esempio che illustra come utilizzare un colore di sistema in una sfumatura, vedere [Usa colori di sistema in una sfumatura](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Usare i colori di sistema in una sfumatura](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
