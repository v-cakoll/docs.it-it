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
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="82606-102">Procedura: Personalizzare i segni di graduazione di un oggetto Slider</span><span class="sxs-lookup"><span data-stu-id="82606-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="82606-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Slider> controllo dotato di segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="82606-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82606-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="82606-104">Example</span></span>  
 <span data-ttu-id="82606-105">Il <xref:System.Windows.Controls.Primitives.TickBar> viene visualizzato quando si imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None>, ovvero il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="82606-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="82606-106">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> che consente di visualizzare i segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="82606-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="82606-107">Il <xref:System.Windows.Controls.Slider.TickPlacement%2A> e <xref:System.Windows.Controls.Slider.TickFrequency%2A> definiscono la posizione dei segni di graduazione e l'intervallo tra di essi.</span><span class="sxs-lookup"><span data-stu-id="82606-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="82606-108">Quando si sposta il <xref:System.Windows.Controls.Primitives.Thumb>, le descrizioni comandi mostrano il valore della <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="82606-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="82606-109">Il <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> definisce proprietà in cui si verificano le descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="82606-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="82606-110">Il <xref:System.Windows.Controls.Primitives.Thumb> spostamenti di tipo corrispondono alla posizione dei segni di graduazione poiché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="82606-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="82606-111">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà per creare segni di graduazione lungo il <xref:System.Windows.Controls.Slider> a intervalli irregolari.</span><span class="sxs-lookup"><span data-stu-id="82606-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="82606-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82606-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="82606-113">[Procedura: Associare un dispositivo di scorrimento al valore della proprietà](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="82606-113">[How to: Bind a Slider to a Property Value](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
