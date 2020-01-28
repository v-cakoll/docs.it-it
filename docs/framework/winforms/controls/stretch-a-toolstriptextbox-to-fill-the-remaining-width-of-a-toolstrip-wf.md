---
title: 'Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742846"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="19f40-102">Procedura: allargare un oggetto ToolStripTextBox in modo da coprire tutta la larghezza di un elemento ToolStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="19f40-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="19f40-103">Quando si imposta la proprietà <xref:System.Windows.Forms.ToolStrip.Stretch%2A> di un controllo <xref:System.Windows.Forms.ToolStrip> su `true`, il controllo riempie il contenitore da fine a fine e viene ridimensionato quando il relativo contenitore viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="19f40-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="19f40-104">In questa configurazione può risultare utile estendere un elemento del controllo, ad esempio un <xref:System.Windows.Forms.ToolStripTextBox>, per riempire lo spazio disponibile e ridimensionare quando il controllo viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="19f40-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="19f40-105">Questa estensione è utile, ad esempio, se si desidera ottenere un aspetto e un comportamento simili alla barra degli indirizzi in Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="19f40-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f40-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="19f40-106">Example</span></span>  
 <span data-ttu-id="19f40-107">Nell'esempio di codice seguente viene fornita una classe derivata da <xref:System.Windows.Forms.ToolStripTextBox> denominata `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="19f40-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="19f40-108">Questa classe esegue l'override del metodo <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> per calcolare la larghezza disponibile del controllo <xref:System.Windows.Forms.ToolStrip> padre dopo che la larghezza combinata di tutti gli altri elementi è stata sottratta.</span><span class="sxs-lookup"><span data-stu-id="19f40-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="19f40-109">Questo esempio di codice fornisce anche una classe <xref:System.Windows.Forms.Form> e una classe `Program` per illustrare il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="19f40-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19f40-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="19f40-110">Compiling the Code</span></span>  
 <span data-ttu-id="19f40-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="19f40-111">This example requires:</span></span>  
  
- <span data-ttu-id="19f40-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="19f40-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f40-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19f40-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="19f40-114">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="19f40-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="19f40-115">Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="19f40-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
