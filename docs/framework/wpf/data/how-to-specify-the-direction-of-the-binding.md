---
title: 'Procedura: specificare la direzione di associazione'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 100130f3dc099d1cf1f216c841e7e1dc1d083f39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556822"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="ac719-102">Procedura: specificare la direzione di associazione</span><span class="sxs-lookup"><span data-stu-id="ac719-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="ac719-103">Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="ac719-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac719-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac719-104">Example</span></span>  
 <span data-ttu-id="ac719-105">Utilizzare il <xref:System.Windows.Data.Binding.Mode%2A> proprietà per specificare la direzione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="ac719-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="ac719-106">L'elenco di enumerazione seguente mostra le opzioni disponibili per gli aggiornamenti di binding:</span><span class="sxs-lookup"><span data-stu-id="ac719-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="ac719-107"><xref:System.Windows.Data.BindingMode.TwoWay> Aggiorna la proprietà di destinazione o la proprietà ogni volta che la proprietà di destinazione o la proprietà di origine modificato.</span><span class="sxs-lookup"><span data-stu-id="ac719-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="ac719-108"><xref:System.Windows.Data.BindingMode.OneWay> Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.</span><span class="sxs-lookup"><span data-stu-id="ac719-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="ac719-109"><xref:System.Windows.Data.BindingMode.OneTime> Aggiorna la proprietà di destinazione solo all'avvio dell'applicazione o quando il <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.</span><span class="sxs-lookup"><span data-stu-id="ac719-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="ac719-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac719-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="ac719-111"><xref:System.Windows.Data.BindingMode.Default> fa sì che il valore predefinito <xref:System.Windows.Data.Binding.Mode%2A> valore della proprietà di destinazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ac719-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="ac719-112">Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="ac719-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="ac719-113">Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac719-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="ac719-114">Per rilevare le modifiche di origine (applicabile a <xref:System.Windows.Data.BindingMode.OneWay> e <xref:System.Windows.Data.BindingMode.TwoWay> associazioni), l'origine deve implementare un meccanismo di notifica di modifica proprietà appropriato, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="ac719-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="ac719-115">Vedere [implementano la notifica di modifiche](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) per un esempio di un <xref:System.ComponentModel.INotifyPropertyChanged> implementazione.</span><span class="sxs-lookup"><span data-stu-id="ac719-115">See [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="ac719-116">Per <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni, è possibile controllare la tempistica degli aggiornamenti di origine mediante l'impostazione di <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac719-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="ac719-117">Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac719-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac719-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac719-118">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="ac719-119">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="ac719-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ac719-120">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ac719-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
