---
title: "Procedura: condividere le proprietà di ridimensionamento tra griglie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8f80d93f9625ff962a3e3fab1f6647678ecf32f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="05c46-102">Procedura: condividere le proprietà di ridimensionamento tra griglie</span><span class="sxs-lookup"><span data-stu-id="05c46-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="05c46-103">In questo esempio viene illustrato come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> elementi per mantenere coerente il ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="05c46-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05c46-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="05c46-104">Example</span></span>  
 <span data-ttu-id="05c46-105">Nell'esempio seguente vengono presentate due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="05c46-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="05c46-106">Il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> associata di <xref:System.Windows.Controls.Grid> è definito nell'elemento padre, <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="05c46-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="05c46-107">L'esempio modifica il valore della proprietà usando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori di proprietà booleana.</span><span class="sxs-lookup"><span data-stu-id="05c46-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="05c46-108">Quando il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> il valore di proprietà è impostato su `true`, ogni membro di riga o colonna di un <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide informazioni sul ridimensionamento, indipendentemente dal contenuto di una riga o colonna.</span><span class="sxs-lookup"><span data-stu-id="05c46-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="05c46-109">...</span><span class="sxs-lookup"><span data-stu-id="05c46-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="05c46-110">Nell'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> genera eventi.</span><span class="sxs-lookup"><span data-stu-id="05c46-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="05c46-111">L'esempio scrive i risultati delle chiamate al metodo <xref:System.Windows.Controls.TextBlock> gli elementi correlati utilizzare metodi get per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="05c46-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="05c46-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05c46-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [<span data-ttu-id="05c46-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="05c46-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
