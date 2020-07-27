---
title: 'Procedura: Implementare una proprietà di dipendenza'
description: Definire una proprietà di dipendenza in Windows Presentation Foundation, eseguendo il backup di una proprietà Common Language Runtime con un campo DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165099"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="eb3dc-103">Procedura: Implementare una proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="eb3dc-103">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="eb3dc-104">In questo esempio viene illustrato come eseguire il backup di una proprietà Common Language Runtime (CLR) con un <xref:System.Windows.DependencyProperty> campo, definendo in tal modo una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-104">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="eb3dc-105">Quando si definiscono proprietà personalizzate e si vuole che supportino molti aspetti della funzionalità [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], inclusi stili, data binding, ereditarietà, animazione e valori predefiniti, è necessario implementarle come proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-105">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb3dc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb3dc-106">Example</span></span>  
 <span data-ttu-id="eb3dc-107">Nell'esempio seguente viene innanzitutto registrata una proprietà di dipendenza chiamando il <xref:System.Windows.DependencyProperty.Register%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-107">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="eb3dc-108">Il nome del campo dell'identificatore utilizzato per archiviare il nome e le caratteristiche della proprietà di dipendenza deve essere l'oggetto <xref:System.Windows.DependencyProperty.Name%2A> scelto per la proprietà di dipendenza come parte della <xref:System.Windows.DependencyProperty.Register%2A> chiamata, accodato dalla stringa letterale `Property` .</span><span class="sxs-lookup"><span data-stu-id="eb3dc-108">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="eb3dc-109">Ad esempio, se si registra una proprietà di dipendenza con un valore <xref:System.Windows.DependencyProperty.Name%2A> di `Location` , il campo identificatore definito per la proprietà di dipendenza deve essere denominato `LocationProperty` .</span><span class="sxs-lookup"><span data-stu-id="eb3dc-109">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="eb3dc-110">In questo esempio, il nome della proprietà di dipendenza e la relativa funzione di accesso CLR è `State` ; il campo identificatore è `StateProperty` , il tipo della proprietà è <xref:System.Boolean> e il tipo che registra la proprietà di dipendenza è `MyStateControl` .</span><span class="sxs-lookup"><span data-stu-id="eb3dc-110">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="eb3dc-111">Se non si riesce a seguire questo criterio di denominazione, la proprietà potrebbe non essere segnalata correttamente nelle finestre di progettazione e alcuni aspetti dell'applicazione di stili del sistema di proprietà potrebbero non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-111">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="eb3dc-112">È anche possibile specificare metadati predefiniti per una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-112">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="eb3dc-113">In questo esempio viene registrato il valore predefinito della proprietà di dipendenza `State` in modo che sia `false`.</span><span class="sxs-lookup"><span data-stu-id="eb3dc-113">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="eb3dc-114">Per ulteriori informazioni su come e perché implementare una proprietà di dipendenza, anziché semplicemente eseguire il backup di una proprietà CLR con un campo privato, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eb3dc-114">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3dc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb3dc-115">See also</span></span>

- [<span data-ttu-id="eb3dc-116">Cenni preliminari sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="eb3dc-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="eb3dc-117">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="eb3dc-117">How-to Topics</span></span>](properties-how-to-topics.md)
