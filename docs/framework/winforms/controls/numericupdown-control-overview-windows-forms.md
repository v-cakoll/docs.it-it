---
title: Cenni preliminari sul controllo NumericUpDown (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 067a8862ee991213e584819e1cf99eddde06e2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a><span data-ttu-id="be219-102">Cenni preliminari sul controllo NumericUpDown (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="be219-102">NumericUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="be219-103">Il <xref:System.Windows.Forms.NumericUpDown> controllo è simile a una combinazione di una casella di testo e una coppia di frecce che l'utente può fare clic per modificare un valore.</span><span class="sxs-lookup"><span data-stu-id="be219-103">The <xref:System.Windows.Forms.NumericUpDown> control looks like a combination of a text box and a pair of arrows that the user can click to adjust a value.</span></span> <span data-ttu-id="be219-104">Il controllo Visualizza e imposta un valore numerico singolo da un elenco di scelte fisse di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="be219-104">The control displays and sets a single numeric value from a list of fixed numeric-value choices.</span></span> <span data-ttu-id="be219-105">L'utente può aumentare e ridurre il numero facendo clic sulla freccia e freccia giù, premendo i tasti freccia su e giù o digitando un numero nella casella di testo inclusa del controllo.</span><span class="sxs-lookup"><span data-stu-id="be219-105">The user can increase and decrease the number by clicking the up and down arrows, by pressing the UP and DOWN ARROW keys, or by typing a number in the text box part of the control.</span></span> <span data-ttu-id="be219-106">Fare clic su freccia su Sposta il numero verso il valore massimo; Fare clic sulla freccia giù sposta il numero verso il valore minimo.</span><span class="sxs-lookup"><span data-stu-id="be219-106">Clicking the UP ARROW key moves the number toward the maximum; clicking the DOWN ARROW key moves the number toward the minimum.</span></span>  
  
 <span data-ttu-id="be219-107">A causa di sua versatilità questo controllo è una scelta ovvia, ad esempio, se si desidera creare un controllo volume per un'applicazione lettore musicale.</span><span class="sxs-lookup"><span data-stu-id="be219-107">Because of its versatile functionality, this control is an obvious choice, for example, if you want to create a volume control for a music player application.</span></span> <span data-ttu-id="be219-108">Il <xref:System.Windows.Forms.NumericUpDown> controllo viene utilizzato in molte applicazioni del Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="be219-108">The <xref:System.Windows.Forms.NumericUpDown> control is used in many Windows Control Panel applications.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="be219-109">Metodi e proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="be219-109">Key Properties and Methods</span></span>  
 <span data-ttu-id="be219-110">I numeri visualizzati nella casella di testo del controllo possono essere una varietà di formati, tra cui esadecimali.</span><span class="sxs-lookup"><span data-stu-id="be219-110">The numbers displayed in the control's text box can be in a variety of formats, including hexadecimal.</span></span> <span data-ttu-id="be219-111">Per ulteriori informazioni, vedere [procedura: impostare il formato per il controllo NumericUpDown Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span><span class="sxs-lookup"><span data-stu-id="be219-111">For more information, see [How to: Set the Format for the Windows Forms NumericUpDown Control](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span></span> <span data-ttu-id="be219-112">Le proprietà principali del controllo sono <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valore predefinito 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valore predefinito: 0), e <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valore 1 (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="be219-112">The key properties of the control are <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (default value 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (default value 0), and <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (default value 1).</span></span> <span data-ttu-id="be219-113">Il <xref:System.Windows.Forms.NumericUpDown.Value%2A> proprietà imposta il numero corrente selezionato nel controllo.</span><span class="sxs-lookup"><span data-stu-id="be219-113">The <xref:System.Windows.Forms.NumericUpDown.Value%2A> property sets the current number selected in the control.</span></span> <span data-ttu-id="be219-114">Il <xref:System.Windows.Forms.NumericUpDown.Increment%2A> proprietà imposta la quantità che il numero viene modificato da quando l'utente fa clic su una freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="be219-114">The <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property sets the amount that the number is adjusted by when the user clicks an up or down arrow.</span></span> <span data-ttu-id="be219-115">Quando lo stato attivo si sposta dal controllo, qualsiasi valore immesso verrà convalidato a fronte di valori numerici minimi e massimo.</span><span class="sxs-lookup"><span data-stu-id="be219-115">When focus moves off the control, any typed input will be validated against the minimum and maximum numeric values.</span></span> <span data-ttu-id="be219-116">È possibile aumentare la velocità con cui il controllo si sposta tra i numeri, quando l'utente preme continuamente l'alto o verso il basso freccia, con la <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="be219-116">You can increase the speed that the control moves through numbers, when the user continuously presses the up or down arrow, with the <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> property.</span></span> <span data-ttu-id="be219-117">I metodi principali del controllo sono <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> e <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="be219-117">The key methods of the control are <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be219-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be219-118">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="be219-119">Controllo NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="be219-119">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="be219-120">Procedura: Impostare il formato per il controllo NumericUpDown Windows Form</span><span class="sxs-lookup"><span data-stu-id="be219-120">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [<span data-ttu-id="be219-121">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="be219-121">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
