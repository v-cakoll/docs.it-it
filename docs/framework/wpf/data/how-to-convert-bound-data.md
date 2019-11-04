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
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458861"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="b76e3-102">Procedura: convertire i dati associati</span><span class="sxs-lookup"><span data-stu-id="b76e3-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="b76e3-103">In questo esempio viene illustrato come applicare la conversione ai dati utilizzati nelle associazioni.</span><span class="sxs-lookup"><span data-stu-id="b76e3-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="b76e3-104">Per convertire i dati durante l'associazione, è necessario creare una classe che implementi l'interfaccia <xref:System.Windows.Data.IValueConverter>, che include i metodi <xref:System.Windows.Data.IValueConverter.Convert%2A> e <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.</span><span class="sxs-lookup"><span data-stu-id="b76e3-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b76e3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b76e3-105">Example</span></span>  
 <span data-ttu-id="b76e3-106">Nell'esempio seguente viene illustrata l'implementazione di un convertitore di data che converte il valore di data passato in modo da visualizzare solo l'anno, il mese e il giorno.</span><span class="sxs-lookup"><span data-stu-id="b76e3-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="b76e3-107">Quando si implementa l'interfaccia <xref:System.Windows.Data.IValueConverter>, è consigliabile decorare l'implementazione con un attributo <xref:System.Windows.Data.ValueConversionAttribute> per indicare agli strumenti di sviluppo i tipi di dati necessari per la conversione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b76e3-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="b76e3-108">Una volta creato un convertitore, è possibile aggiungerlo come risorsa nel file di [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b76e3-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="b76e3-109">Nell'esempio seguente *src* esegue il mapping allo spazio dei nomi in cui è definito *DateConverter* .</span><span class="sxs-lookup"><span data-stu-id="b76e3-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="b76e3-110">Infine, è possibile usare il convertitore nell'associazione usando la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="b76e3-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="b76e3-111">Nell'esempio seguente il contenuto di testo del <xref:System.Windows.Controls.TextBlock> viene associato a *StartDate*, che è una proprietà di un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="b76e3-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="b76e3-112">Le risorse di stile a cui viene fatto riferimento nell'esempio precedente sono definite in una sezione delle risorse non illustrata in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b76e3-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76e3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b76e3-113">See also</span></span>

- [<span data-ttu-id="b76e3-114">Implementare la convalida dell'associazione</span><span class="sxs-lookup"><span data-stu-id="b76e3-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="b76e3-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b76e3-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b76e3-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b76e3-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
