---
title: "Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 57edaa173b85bc06c6859b08d3edec281e1b8942
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372858"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="ad59a-102">Procedura: Compilare una finestra di dialogo dell'interfaccia utente standard utilizzando l'elemento Grid</span><span class="sxs-lookup"><span data-stu-id="ad59a-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="ad59a-103">In questo esempio viene illustrato come creare uno standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] finestra di dialogo tramite il <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="ad59a-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad59a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad59a-104">Example</span></span>  
 <span data-ttu-id="ad59a-105">L'esempio seguente crea una finestra di dialogo, ad esempio la **eseguiti** nella finestra di dialogo di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ad59a-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="ad59a-106">Nell'esempio viene creata una <xref:System.Windows.Controls.Grid> e Usa le <xref:System.Windows.Controls.ColumnDefinition> e <xref:System.Windows.Controls.RowDefinition> classi per definire cinque colonne e quattro righe.</span><span class="sxs-lookup"><span data-stu-id="ad59a-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="ad59a-107">L'esempio aggiunge quindi e posiziona un' <xref:System.Windows.Controls.Image>, `RunIcon.png`, per rappresentare l'immagine che si trova nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ad59a-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="ad59a-108">L'immagine viene inserito nella colonna e riga del primo il <xref:System.Windows.Controls.Grid> (angolo in alto a sinistra).</span><span class="sxs-lookup"><span data-stu-id="ad59a-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="ad59a-109">Successivamente, nell'esempio viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento alla prima colonna, che si estende le colonne rimanenti della prima riga.</span><span class="sxs-lookup"><span data-stu-id="ad59a-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="ad59a-110">Aggiunge un'altra <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga nella prima colonna, per rappresentare il **Open** casella di testo.</span><span class="sxs-lookup"><span data-stu-id="ad59a-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="ad59a-111">Oggetto <xref:System.Windows.Controls.TextBlock> indicato di seguito, che rappresenta l'area di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="ad59a-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="ad59a-112">Infine, l'esempio aggiunge tre <xref:System.Windows.Controls.Button> elementi nella riga finale, che rappresentano le **OK**, **Annulla**, e **Sfoglia** gli eventi.</span><span class="sxs-lookup"><span data-stu-id="ad59a-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ad59a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad59a-113">See also</span></span>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="ad59a-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="ad59a-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="ad59a-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ad59a-115">How-to Topics</span></span>](grid-how-to-topics.md)
