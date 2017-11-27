---
title: 'Procedura: modificare l''aspetto di un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="28549-102">Procedura: modificare l'aspetto di un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="28549-102">How to: Change the Appearance of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="28549-103">È possibile modificare l'aspetto di un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di progettazione impostando le proprietà o in fase di esecuzione mediante la gestione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento.</span><span class="sxs-lookup"><span data-stu-id="28549-103">You can change the appearance of a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time by setting properties or at run time by handling the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event.</span></span>  
  
 <span data-ttu-id="28549-104">Le proprietà impostate in fase di progettazione quando è selezionata la sezione del modello di elemento del controllo verranno ripetute per ogni <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="28549-104">Properties that you set at design time when the item template section of the control is selected will be repeated for each <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> at run time.</span></span> <span data-ttu-id="28549-105">Proprietà relative all'aspetto del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo sarà visibile in fase di esecuzione sono stati rilevati solo se una parte del contenitore viene lasciato (ad esempio, se il <xref:System.Windows.Forms.Control.Padding%2A> è impostata su un valore elevato).</span><span class="sxs-lookup"><span data-stu-id="28549-105">Appearance-related properties of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control itself will be visible at run time only if a part of the container is left uncovered (for example, if the <xref:System.Windows.Forms.Control.Padding%2A> property is set to a large value).</span></span>  
  
 <span data-ttu-id="28549-106">In fase di esecuzione, le proprietà correlate all'aspetto possono essere impostate in base alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="28549-106">At run time, appearance-related properties can be set based on conditions.</span></span> <span data-ttu-id="28549-107">In un'applicazione di pianificazione, ad esempio, è possibile modificare il colore di sfondo di un elemento per avvisare gli utenti quando un elemento è scaduto.</span><span class="sxs-lookup"><span data-stu-id="28549-107">For example, in a scheduling application, you might change the background color of an item to warn users when an item is past due.</span></span> <span data-ttu-id="28549-108">Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> gestore dell'evento, se si imposta una proprietà in un'istruzione condizionale, ad esempio `If…Then`, è necessario utilizzare anche un `Else` clausola per specificare l'aspetto quando non viene soddisfatta la condizione.</span><span class="sxs-lookup"><span data-stu-id="28549-108">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, if you set a property in a conditional statement such as `If…Then`, you must also use an `Else` clause to specify the appearance when the condition is not met.</span></span>  
  
### <a name="to-change-the-appearance-at-design-time"></a><span data-ttu-id="28549-109">Per modificare l'aspetto in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="28549-109">To change the appearance at design time</span></span>  
  
1.  <span data-ttu-id="28549-110">In Progettazione Windows Form, selezionare l'area del modello (superiore) dell'elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="28549-110">In the Windows Forms Designer, select the item template (upper) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="28549-111">Nella finestra Proprietà, selezionare una proprietà e modificare il valore.</span><span class="sxs-lookup"><span data-stu-id="28549-111">In the Properties window, select a property and change the value.</span></span> <span data-ttu-id="28549-112">Proprietà comuni che influiscono sull'aspetto includono <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, e <xref:System.Windows.Forms.Control.ForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="28549-112">Common properties that affect appearance include <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, and <xref:System.Windows.Forms.Control.ForeColor%2A>.</span></span>  
  
### <a name="to-change-the-appearance-at-run-time"></a><span data-ttu-id="28549-113">Per modificare l'aspetto in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="28549-113">To change the appearance at run time</span></span>  
  
1.  <span data-ttu-id="28549-114">Nell'elenco a discesa Event dell'editor di codice, selezionare **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="28549-114">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
2.  <span data-ttu-id="28549-115">Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> gestore, aggiungere il codice per impostare le proprietà:</span><span class="sxs-lookup"><span data-stu-id="28549-115">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add code to set the properties:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="28549-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="28549-116">Example</span></span>  
 <span data-ttu-id="28549-117">Alcune personalizzazioni comuni per la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo include la visualizzazione delle righe in colori alternati e modificare il colore di un campo in base a una condizione.</span><span class="sxs-lookup"><span data-stu-id="28549-117">Some common customizations for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control include displaying the rows in alternating colors and changing the color of a field based on a condition.</span></span> <span data-ttu-id="28549-118">Nell'esempio seguente viene illustrato come eseguire queste personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="28549-118">The following example shows how to perform these customizations.</span></span> <span data-ttu-id="28549-119">In questo esempio si presuppone un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo associato alla tabella Products del database Northwind.</span><span class="sxs-lookup"><span data-stu-id="28549-119">This example assumes that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that is bound to the Products table in the Northwind database.</span></span>  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 <span data-ttu-id="28549-120">Si noti che, per entrambe queste personalizzazioni, è necessario fornire il codice per impostare le proprietà per entrambi i lati della condizione.</span><span class="sxs-lookup"><span data-stu-id="28549-120">Note that for both of these customizations, you must provide code to set the properties for both sides of the condition.</span></span> <span data-ttu-id="28549-121">Se non si specifica il `Else` condizione, verranno visualizzati risultati imprevisti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="28549-121">If you do not specify the `Else` condition, you will see unexpected results at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28549-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28549-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [<span data-ttu-id="28549-123">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="28549-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="28549-124">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="28549-124">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="28549-125">Procedura: Visualizzare i dati associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="28549-125">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="28549-126">Procedura: Visualizzare i controlli non associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="28549-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="28549-127">Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="28549-127">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
