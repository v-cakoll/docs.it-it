---
title: "Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard usando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923412"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="28af9-102">Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard usando l'elemento Grid</span><span class="sxs-lookup"><span data-stu-id="28af9-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="28af9-103">Questo esempio illustra come creare una finestra di [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialogo standard usando l' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="28af9-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28af9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="28af9-104">Example</span></span>  
 <span data-ttu-id="28af9-105">Nell'esempio seguente viene creata una finestra di dialogo come la finestra di dialogo **Esegui** nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="28af9-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="28af9-106">Nell'esempio viene creato <xref:System.Windows.Controls.Grid> un oggetto e <xref:System.Windows.Controls.ColumnDefinition> vengono <xref:System.Windows.Controls.RowDefinition> utilizzate le classi e per definire cinque colonne e quattro righe.</span><span class="sxs-lookup"><span data-stu-id="28af9-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="28af9-107">Nell'esempio viene quindi aggiunto e posizionato <xref:System.Windows.Controls.Image>un `RunIcon.png`oggetto,, per rappresentare l'immagine presente nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="28af9-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="28af9-108">L'immagine viene posizionata nella prima colonna e nella prima riga <xref:System.Windows.Controls.Grid> di (angolo superiore sinistro).</span><span class="sxs-lookup"><span data-stu-id="28af9-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="28af9-109">Successivamente, nell'esempio viene aggiunto <xref:System.Windows.Controls.TextBlock> un elemento alla prima colonna, che si estende sulle colonne rimanenti della prima riga.</span><span class="sxs-lookup"><span data-stu-id="28af9-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="28af9-110">Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga della prima colonna, per rappresentare la casella di testo **aperta** .</span><span class="sxs-lookup"><span data-stu-id="28af9-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="28af9-111"><xref:System.Windows.Controls.TextBlock> Segue, che rappresenta l'area di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="28af9-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="28af9-112">Infine, nell'esempio vengono aggiunti <xref:System.Windows.Controls.Button> tre elementi alla riga finale, che rappresentano gli eventi **OK**, **Cancel**e **Browse** .</span><span class="sxs-lookup"><span data-stu-id="28af9-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="28af9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28af9-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="28af9-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="28af9-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="28af9-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="28af9-115">How-to Topics</span></span>](grid-how-to-topics.md)
