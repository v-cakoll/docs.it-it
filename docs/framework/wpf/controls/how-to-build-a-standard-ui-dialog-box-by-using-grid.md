---
title: "Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: d0b24e320c2a341b069e1c9c3e8b6d5e93076733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551882"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="cbb3e-102">Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid</span><span class="sxs-lookup"><span data-stu-id="cbb3e-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="cbb3e-103">In questo esempio viene illustrato come creare uno standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] la finestra di dialogo utilizzando il <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbb3e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbb3e-104">Example</span></span>  
 <span data-ttu-id="cbb3e-105">L'esempio seguente crea una finestra di dialogo come il **eseguire** nella finestra di dialogo di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="cbb3e-106">Nell'esempio viene creato un <xref:System.Windows.Controls.Grid> e utilizza il <xref:System.Windows.Controls.ColumnDefinition> e <xref:System.Windows.Controls.RowDefinition> classi per definire cinque colonne e quattro righe.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="cbb3e-107">Nell'esempio viene quindi aggiunto e posiziona un <xref:System.Windows.Controls.Image>, `RunIcon.png`, per rappresentare l'immagine che viene trovato nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="cbb3e-108">L'immagine viene posizionata nella prima colonna e riga del <xref:System.Windows.Controls.Grid> (nell'angolo superiore sinistro).</span><span class="sxs-lookup"><span data-stu-id="cbb3e-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="cbb3e-109">In seguito, viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento per la prima colonna, che si estende le colonne rimanenti della prima riga.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="cbb3e-110">Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento della seconda riga nella prima colonna, per rappresentare il **aprire** casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="cbb3e-111">Oggetto <xref:System.Windows.Controls.TextBlock> indicato di seguito, che rappresenta l'area di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="cbb3e-112">Infine, l'esempio aggiunge tre <xref:System.Windows.Controls.Button> elementi per la riga finale, che rappresentano il **OK**, **Annulla**, e **Sfoglia** eventi.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cbb3e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbb3e-113">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [<span data-ttu-id="cbb3e-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="cbb3e-114">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="cbb3e-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="cbb3e-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
