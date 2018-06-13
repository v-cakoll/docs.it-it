---
title: 'Procedura: convertire i dati associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 526305f32280fb75e95538b9014c34c11ed8bffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556640"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="df561-102">Procedura: convertire i dati associati</span><span class="sxs-lookup"><span data-stu-id="df561-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="df561-103">In questo esempio viene illustrato come applicare la conversione in dati utilizzati nelle associazioni.</span><span class="sxs-lookup"><span data-stu-id="df561-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="df561-104">Per convertire i dati durante l'associazione, è necessario creare una classe che implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, che include il <xref:System.Windows.Data.IValueConverter.Convert%2A> e <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="df561-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df561-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="df561-105">Example</span></span>  
 <span data-ttu-id="df561-106">Nell'esempio seguente viene illustrata l'implementazione di un convertitore di tipi di data che converte il valore di data passato in modo che visualizza solo l'anno, mese e giorno.</span><span class="sxs-lookup"><span data-stu-id="df561-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="df561-107">Quando si implementa il <xref:System.Windows.Data.IValueConverter> interfaccia, è buona norma decorare l'implementazione con un <xref:System.Windows.Data.ValueConversionAttribute> attributo per indicare allo sviluppo di strumenti di tipi di dati coinvolti nella conversione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="df561-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="df561-108">Dopo aver creato un convertitore, è possibile aggiungere come risorsa nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span><span class="sxs-lookup"><span data-stu-id="df561-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="df561-109">Nell'esempio seguente, *src* esegue il mapping allo spazio dei nomi in cui *DateConverter* è definito.</span><span class="sxs-lookup"><span data-stu-id="df561-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="df561-110">Infine, è possibile utilizzare il convertitore nell'associazione utilizzando la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="df561-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="df561-111">Nell'esempio seguente, il contenuto di testo di <xref:System.Windows.Controls.TextBlock> è associato a *StartDate*, che è una proprietà di un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="df561-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="df561-112">Le risorse di stile a cui fa riferimento nell'esempio precedente sono definite in una sezione di risorsa non è stata illustrata in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="df561-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df561-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df561-113">See Also</span></span>  
 [<span data-ttu-id="df561-114">Implementare la convalida dell'associazione</span><span class="sxs-lookup"><span data-stu-id="df561-114">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="df561-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="df561-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="df561-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="df561-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
