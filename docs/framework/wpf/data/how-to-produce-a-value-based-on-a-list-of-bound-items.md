---
title: 'Procedura: produrre un valore in base a un elenco di elementi associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: d61631949382c177000b85aa8f4e093c3532c7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556835"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="0a9e3-102">Procedura: produrre un valore in base a un elenco di elementi associati</span><span class="sxs-lookup"><span data-stu-id="0a9e3-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="0a9e3-103"><xref:System.Windows.Data.MultiBinding> Consente di associare una proprietà di destinazione dell'associazione a un elenco delle proprietà di origine e quindi applicare la logica per produrre un valore con gli input specificati.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="0a9e3-104">In questo esempio viene illustrato come utilizzare <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a9e3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a9e3-105">Example</span></span>  
 <span data-ttu-id="0a9e3-106">Nell'esempio seguente, `NameListData` fa riferimento a una raccolta di oggetti `PersonName`, che contengono due proprietà: `firstName` e `lastName`.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="0a9e3-107">L'esempio seguente produce un <xref:System.Windows.Controls.TextBlock> che mostra i nomi e il cognome di una persona con il nome dell'ultimo prima.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="0a9e3-108">Per comprendere come viene generato il formato con il cognome prima del nome, osservare l'implementazione di `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="0a9e3-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="0a9e3-109">L'oggetto `NameConverter` implementa l'interfaccia <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="0a9e3-110">`NameConverter` accetta i valori dei singoli binding e li archivia nella matrice di oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="0a9e3-111">L'ordine in cui il <xref:System.Windows.Data.Binding> gli elementi vengono visualizzati sotto il <xref:System.Windows.Data.MultiBinding> elemento è l'ordine in cui sono archiviati tali valori nella matrice.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="0a9e3-112">Il valore della <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> fa riferimento l'argomento di parametro dell'attributo di <xref:System.Windows.Data.MultiBinding.Converter%2A> (metodo), che esegue una modifica del parametro per determinare la modalità di formattazione del nome.</span><span class="sxs-lookup"><span data-stu-id="0a9e3-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9e3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a9e3-113">See Also</span></span>  
 [<span data-ttu-id="0a9e3-114">Convertire i dati associati</span><span class="sxs-lookup"><span data-stu-id="0a9e3-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="0a9e3-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="0a9e3-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0a9e3-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="0a9e3-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
