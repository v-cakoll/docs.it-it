---
title: Cenni preliminari sul controllo CheckBox (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="4a056-102">Cenni preliminari sul controllo CheckBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="4a056-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="4a056-103">Il controllo di Windows Form <xref:System.Windows.Forms.CheckBox> indica se una determinata condizione è attiva o disattivata.</span><span class="sxs-lookup"><span data-stu-id="4a056-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="4a056-104">Viene usato comunemente per presentare all'utente la selezione di valori Sì/No o True/False.</span><span class="sxs-lookup"><span data-stu-id="4a056-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="4a056-105">È possibile usare i controlli della casella di controllo in gruppi, per visualizzare e consentire all'utente la selezione di una o più opzioni.</span><span class="sxs-lookup"><span data-stu-id="4a056-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="4a056-106">Il controllo casella di controllo è simile al controllo pulsante di opzione in quanto ognuna viene utilizzata per indicare una selezione effettuata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4a056-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="4a056-107">Si differenziano in cui è possibile selezionare solo un pulsante di opzione in un gruppo alla volta.</span><span class="sxs-lookup"><span data-stu-id="4a056-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="4a056-108">Con il controllo casella di controllo, tuttavia, è possibile selezionare un numero qualsiasi di caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="4a056-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="4a056-109">Una casella di controllo possono essere collegata a elementi in un database utilizzando l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="4a056-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="4a056-110">Inoltre è possibile raggruppare più caselle di controllo utilizzando il <xref:System.Windows.Forms.GroupBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="4a056-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="4a056-111">Ciò è utile per l'aspetto visivo, nonché per la progettazione dell'interfaccia utente, poiché i controlli raggruppati possono essere spostati insieme nella finestra di progettazione form.</span><span class="sxs-lookup"><span data-stu-id="4a056-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="4a056-112">Per ulteriori informazioni, vedere [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) e [controllo GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a056-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="4a056-113">Il <xref:System.Windows.Forms.CheckBox> controllo ha due proprietà importanti, <xref:System.Windows.Forms.CheckBox.Checked%2A> e <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a056-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="4a056-114">Il <xref:System.Windows.Forms.CheckBox.Checked%2A> restituisce proprietà `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="4a056-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="4a056-115">Il <xref:System.Windows.Forms.CheckBox.CheckState%2A> restituisce proprietà <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; oppure, se il <xref:System.Windows.Forms.CheckBox.ThreeState%2A> è impostata su `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> potrebbero restituire anche <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="4a056-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="4a056-116">In stato indeterminato, viene visualizzata come inattiva per indicare che l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4a056-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a056-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a056-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="4a056-118">Procedura: Impostare opzioni con i controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a056-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="4a056-119">Procedura: Rispondere alla selezione di controlli CheckBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a056-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="4a056-120">Controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="4a056-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
