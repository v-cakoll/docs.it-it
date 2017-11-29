---
title: 'Procedura: utilizzare una classe Control Rendering'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff10cd12889750e3d32fcfce080d472f40bb9c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="8e907-102">Procedura: utilizzare una classe Control Rendering</span><span class="sxs-lookup"><span data-stu-id="8e907-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="8e907-103">In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Forms.ComboBoxRenderer> classe per il rendering di casella di controllo sulla freccia a discesa di una casella combinata.</span><span class="sxs-lookup"><span data-stu-id="8e907-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="8e907-104">L'esempio è costituito il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di un semplice controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8e907-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="8e907-105">Il <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> proprietà viene utilizzata per determinare se sono abilitati nell'area client di finestre dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e907-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="8e907-106">Se gli stili di visualizzazione sono attive, il <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> metodo esegue il rendering la freccia a discesa con gli stili visivi; in caso contrario, il <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> metodo esegue il rendering la freccia a discesa in stile classico di Windows.</span><span class="sxs-lookup"><span data-stu-id="8e907-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e907-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e907-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e907-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8e907-108">Compiling the Code</span></span>  
 <span data-ttu-id="8e907-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e907-109">This example requires:</span></span>  
  
-   <span data-ttu-id="8e907-110">Un controllo personalizzato derivato dalla <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="8e907-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="8e907-111">Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8e907-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="8e907-112">I riferimenti al <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, e <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8e907-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e907-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e907-113">See Also</span></span>  
 [<span data-ttu-id="8e907-114">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="8e907-114">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
