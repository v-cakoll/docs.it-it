---
title: 'Procedura: Personalizzare i segni di graduazione di un oggetto Slider'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 3b32bbedb5f654ce75e90a827eb0c4dba1d4d345
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910689"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Procedura: Personalizzare i segni di graduazione di un oggetto Slider
In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Slider> controllo dotato di segni di graduazione.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.TickBar> viene visualizzato quando si imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None>, ovvero il valore predefinito.  
  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> che consente di visualizzare i segni di graduazione. Il <xref:System.Windows.Controls.Slider.TickPlacement%2A> e <xref:System.Windows.Controls.Slider.TickFrequency%2A> definiscono la posizione dei segni di graduazione e l'intervallo tra di essi. Quando si sposta il <xref:System.Windows.Controls.Primitives.Thumb>, le descrizioni comandi mostrano il valore della <xref:System.Windows.Controls.Slider>. Il <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> definisce proprietà in cui si verificano le descrizioni comandi. Il <xref:System.Windows.Controls.Primitives.Thumb> spostamenti di tipo corrispondono alla posizione dei segni di graduazione poiché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostata su `true`.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà per creare segni di graduazione lungo il <xref:System.Windows.Controls.Slider> a intervalli irregolari.  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [Procedura: Associare un dispositivo di scorrimento al valore della proprietà](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
