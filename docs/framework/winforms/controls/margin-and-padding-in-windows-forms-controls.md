---
title: Margini e spaziatura nei controlli Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22d8a73963a8f9f1e3d8b80b6c16f189e0221c55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="f04d9-102">Margini e spaziatura nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="f04d9-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="f04d9-103">Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="f04d9-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="f04d9-104">A tale scopo, lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> offre diversi strumenti di layout.</span><span class="sxs-lookup"><span data-stu-id="f04d9-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="f04d9-105">Due tra le più importanti sono le proprietà <xref:System.Windows.Forms.Control.Margin%2A> e <xref:System.Windows.Forms.Control.Padding%2A>.</span><span class="sxs-lookup"><span data-stu-id="f04d9-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="f04d9-106">La proprietà <xref:System.Windows.Forms.Control.Margin%2A> definisce lo spazio intorno al controllo per mantenere gli altri controlli a una specifica distanza dai bordi del controllo stesso.</span><span class="sxs-lookup"><span data-stu-id="f04d9-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="f04d9-107">La proprietà <xref:System.Windows.Forms.Control.Padding%2A> definisce lo spazio all'interno di un controllo per mantenere il contenuto del controllo, ad esempio il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A>, a una specifica distanza dai bordi del controllo stesso.</span><span class="sxs-lookup"><span data-stu-id="f04d9-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="f04d9-108">L'illustrazione seguente mostra le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> in un controllo.</span><span class="sxs-lookup"><span data-stu-id="f04d9-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="f04d9-109">![Spaziatura e margini per Windows Form controlli](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="f04d9-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="f04d9-110">È disponibile supporto in fase di progettazione per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f04d9-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="f04d9-111">Vedere anche [procedura dettagliata: disposizione di controlli Windows Form usando spaziatura, margini e la proprietà AutoSize](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f04d9-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04d9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04d9-112">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
