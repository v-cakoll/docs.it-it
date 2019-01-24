---
title: 'Procedura: Condividere le proprietà di ridimensionamento tra griglie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: e415cb8bf5d2eb53926ae885ba18685390a61201
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694100"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="8fe37-102">Procedura: Condividere le proprietà di ridimensionamento tra griglie</span><span class="sxs-lookup"><span data-stu-id="8fe37-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="8fe37-103">In questo esempio mostra come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> elementi per mantenere coerente il ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="8fe37-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe37-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fe37-104">Example</span></span>  
 <span data-ttu-id="8fe37-105">Nell'esempio seguente vengono introdotti due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="8fe37-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="8fe37-106">Il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> proprietà collegata <xref:System.Windows.Controls.Grid> viene definito nell'elemento padre <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="8fe37-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="8fe37-107">L'esempio modifica il valore della proprietà usando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori della proprietà booleana.</span><span class="sxs-lookup"><span data-stu-id="8fe37-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="8fe37-108">Quando la <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> valore della proprietà è impostato su `true`, ogni membro di riga o colonna di una <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide le informazioni sul ridimensionamento, indipendentemente dal contenuto di una riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="8fe37-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="8fe37-109">...</span><span class="sxs-lookup"><span data-stu-id="8fe37-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8fe37-110">L'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generati dagli eventi.</span><span class="sxs-lookup"><span data-stu-id="8fe37-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="8fe37-111">L'esempio scrive i risultati di chiamate ai metodi <xref:System.Windows.Controls.TextBlock> gli elementi correlati Usa metodi get per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="8fe37-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8fe37-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe37-112">See also</span></span>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="8fe37-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="8fe37-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
