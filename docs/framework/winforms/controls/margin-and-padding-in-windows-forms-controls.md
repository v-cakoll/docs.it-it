---
title: Margini e spaziatura nei controlli
description: Informazioni su come aggiungere margini e spaziatura interna nei controlli Windows Form con le proprietà Margin e Padding.
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: 4279f39bb4f89fbda8be472f49c8e60853abcac6
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174484"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="e78b4-103">Margini e spaziatura nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="e78b4-103">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="e78b4-104">Per molte applicazioni è estremamente importante la sistemazione precisa dei controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="e78b4-104">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="e78b4-105">A tale scopo, lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> offre diversi strumenti di layout.</span><span class="sxs-lookup"><span data-stu-id="e78b4-105">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="e78b4-106">Due tra le più importanti sono le proprietà <xref:System.Windows.Forms.Control.Margin%2A> e <xref:System.Windows.Forms.Control.Padding%2A>.</span><span class="sxs-lookup"><span data-stu-id="e78b4-106">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="e78b4-107">La proprietà <xref:System.Windows.Forms.Control.Margin%2A> definisce lo spazio intorno al controllo per mantenere gli altri controlli a una specifica distanza dai bordi del controllo stesso.</span><span class="sxs-lookup"><span data-stu-id="e78b4-107">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="e78b4-108">La proprietà <xref:System.Windows.Forms.Control.Padding%2A> definisce lo spazio all'interno di un controllo per mantenere il contenuto del controllo, ad esempio il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A>, a una specifica distanza dai bordi del controllo stesso.</span><span class="sxs-lookup"><span data-stu-id="e78b4-108">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="e78b4-109">L'illustrazione seguente mostra le proprietà <xref:System.Windows.Forms.Control.Padding%2A> e <xref:System.Windows.Forms.Control.Margin%2A> in un controllo.</span><span class="sxs-lookup"><span data-stu-id="e78b4-109">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="e78b4-110">![Spaziatura e margine per controlli Windows Form](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="e78b4-110">![Padding And Margin for Windows Forms Controls](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="e78b4-111">È disponibile supporto in fase di progettazione per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e78b4-111">There is design-time support for this feature in Visual Studio.</span></span> <span data-ttu-id="e78b4-112">Vedere anche [procedura dettagliata: layout Windows Forms controlli con spaziatura interna, margini e proprietà AutoSize](windows-forms-controls-padding-autosize.md).</span><span class="sxs-lookup"><span data-stu-id="e78b4-112">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78b4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e78b4-113">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
