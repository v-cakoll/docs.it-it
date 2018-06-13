---
title: 'Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537720"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="ccf74-102">Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="ccf74-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="ccf74-103">Quando si imposta la <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà di un <xref:System.Windows.Forms.ToolStrip> il controllo a `true`, il controllo occupa il proprio contenitore totalmente e viene ridimensionato quando il contenitore si ridimensiona.</span><span class="sxs-lookup"><span data-stu-id="ccf74-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="ccf74-104">In questa configurazione, potrebbe essere utile per l'estensione di un elemento nel controllo, ad esempio un <xref:System.Windows.Forms.ToolStripTextBox>, per riempire lo spazio disponibile e ridimensionarlo quando il controllo viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="ccf74-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="ccf74-105">Questa soluzione è utile, ad esempio, se si desidera ottenere un aspetto e comportamento simile alla barra degli indirizzi di Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ccf74-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccf74-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ccf74-106">Example</span></span>  
 <span data-ttu-id="ccf74-107">Esempio di codice seguente fornisce una classe derivata da <xref:System.Windows.Forms.ToolStripTextBox> chiamato `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="ccf74-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="ccf74-108">Questa classe esegue l'override di <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> metodo per calcolare la larghezza dell'elemento padre disponibile <xref:System.Windows.Forms.ToolStrip> controllo dopo la larghezza combinata di tutti gli altri elementi è stato sottratto.</span><span class="sxs-lookup"><span data-stu-id="ccf74-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="ccf74-109">Questo esempio di codice fornisce inoltre un <xref:System.Windows.Forms.Form> classe e un `Program` classe per illustrare il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="ccf74-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ccf74-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ccf74-110">Compiling the Code</span></span>  
 <span data-ttu-id="ccf74-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccf74-111">This example requires:</span></span>  
  
-   <span data-ttu-id="ccf74-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ccf74-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf74-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccf74-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ccf74-114">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccf74-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="ccf74-115">Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ccf74-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
