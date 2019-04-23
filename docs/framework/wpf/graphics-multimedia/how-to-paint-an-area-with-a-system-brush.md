---
title: "Procedura: Disegnare un'area con un pennello di sistema"
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: e713903e2cfbb63cb64ceb94621317f9e76dea70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195046"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Procedura: Disegnare un'area con un pennello di sistema
Il <xref:System.Windows.SystemColors> classe fornisce accesso ai pennelli di sistema e i colori, ad esempio <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, e <xref:System.Windows.SystemColors.DesktopBrush%2A>. Un pennello di sistema è un <xref:System.Windows.Media.SolidColorBrush> che disegna un'area con il colore di sistema specificato. Un pennello di sistema produce sempre un riempimento a tinta unita e non può essere usato per creare una sfumatura.  
  
 È possibile usare i pennelli di sistema come risorsa statica o dinamica. Usare una risorsa dinamica se si desidera che il pennello si aggiorni automaticamente in caso di modifica mentre l'applicazione è in esecuzione. In caso contrario, usare una risorsa statica. La classe SystemColors contiene un'ampia gamma di proprietà statiche che seguono una rigida convenzione di denominazione:  
  
-   *\<SystemColor>* Brush  
  
     Ottiene un riferimento statico a una <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
-   *\<SystemColor>* BrushKey  
  
     Ottiene un riferimento dinamico a un <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
-   *\<SystemColor>* Color  
  
     Ottiene un riferimento statico a una <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
-   *\<SystemColor>* ColorKey  
  
     Ottiene un riferimento dinamico al <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
 È un colore di sistema un <xref:System.Windows.Media.Color> struttura che può essere usato per configurare un pennello. Ad esempio, è possibile creare una sfumatura con colori di sistema impostando il <xref:System.Windows.Media.GradientStop.Color%2A> delle proprietà di un <xref:System.Windows.Media.LinearGradientBrush> cursori sfumatura con colori di sistema dell'oggetto. Per un esempio, vedere [Usa i colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un riferimento di pennello di sistema dinamico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 L'esempio seguente usa un riferimento di pennello di sistema statico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Per un esempio che illustra come usare un colore di sistema in una sfumatura, vedere [Usa colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Vedere anche

- [Usare i colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
