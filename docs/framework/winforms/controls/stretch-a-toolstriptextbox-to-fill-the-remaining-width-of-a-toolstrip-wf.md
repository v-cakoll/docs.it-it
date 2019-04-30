---
title: 'Procedura: Allargare ToolStripTextBox la parte rimanente di un controllo ToolStrip (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 707fd2e470a9be1d61d2878eeff845b3cad270db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971925"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="3a442-102">Procedura: Allargare ToolStripTextBox la parte rimanente di un controllo ToolStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="3a442-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="3a442-103">Quando si imposta il <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà di un <xref:System.Windows.Forms.ToolStrip> il controllo a `true`, il controllo riempimento dall'inizio alla fine del contenitore e ridimensiona quando si ridimensiona il relativo contenitore.</span><span class="sxs-lookup"><span data-stu-id="3a442-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="3a442-104">In questa configurazione, si potrebbe risultare utile per estendere un elemento nel controllo, ad esempio un <xref:System.Windows.Forms.ToolStripTextBox>, per riempire lo spazio disponibile e ridimensionati quando il controllo viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="3a442-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="3a442-105">Questa estensione è utile, ad esempio, se si vuole ottenere un aspetto e comportamento simile alla barra degli indirizzi in Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3a442-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a442-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a442-106">Example</span></span>  
 <span data-ttu-id="3a442-107">Esempio di codice seguente fornisce una classe derivata da <xref:System.Windows.Forms.ToolStripTextBox> chiamato `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="3a442-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="3a442-108">Questa classe esegue l'override di <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> metodo per calcolare la larghezza dell'elemento padre disponibile <xref:System.Windows.Forms.ToolStrip> controllo dopo che la larghezza combinata di tutti gli altri elementi è stato sottratto.</span><span class="sxs-lookup"><span data-stu-id="3a442-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="3a442-109">Questo esempio di codice fornisce anche un <xref:System.Windows.Forms.Form> classe e un `Program` classe dimostrano il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="3a442-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a442-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3a442-110">Compiling the Code</span></span>  
 <span data-ttu-id="3a442-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a442-111">This example requires:</span></span>  
  
- <span data-ttu-id="3a442-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3a442-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a442-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a442-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3a442-114">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3a442-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="3a442-115">Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3a442-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
