---
title: 'Procedura: personalizzare i segni di graduazione di un controllo Slider'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 045a2f540a37cdea84d2bf2f3ed1e74e122bdbb5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388306"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Procedura: personalizzare i segni di graduazione di un controllo Slider
In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Slider> controllo dotato di segni di graduazione.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.TickBar> viene visualizzato quando si imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None>, ovvero il valore predefinito.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> che consente di visualizzare i segni di graduazione. Il <xref:System.Windows.Controls.Slider.TickPlacement%2A> e <xref:System.Windows.Controls.Slider.TickFrequency%2A> definiscono la posizione dei segni di graduazione e l'intervallo tra di essi. Quando si sposta il <xref:System.Windows.Controls.Primitives.Thumb>, le descrizioni comandi mostrano il valore della <xref:System.Windows.Controls.Slider>. Il <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> definisce proprietà in cui si verificano le descrizioni comandi. Il <xref:System.Windows.Controls.Primitives.Thumb> spostamenti di tipo corrispondono alla posizione dei segni di graduazione poiché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostata su `true`.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà per creare segni di graduazione lungo il <xref:System.Windows.Controls.Slider> a intervalli irregolari.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Procedure relative a Slider](https://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
