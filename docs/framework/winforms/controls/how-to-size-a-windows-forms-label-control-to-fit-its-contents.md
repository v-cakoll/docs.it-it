---
title: 'Procedura: ridimensionare un controllo Label Windows Form in base al contenuto'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="aa86d-102">Procedura: ridimensionare un controllo Label Windows Form in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="aa86d-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="aa86d-103">Windows Form <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o automaticamente ridimensionato in base alla lunghezza della didascalia.</span><span class="sxs-lookup"><span data-stu-id="aa86d-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="aa86d-104">Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie maggiore o minore, particolarmente utile se la didascalia verrà modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aa86d-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="aa86d-105">Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto</span><span class="sxs-lookup"><span data-stu-id="aa86d-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="aa86d-106">Impostare il relativo <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="aa86d-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="aa86d-107">Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostato su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà eseguirà il wrapping alla riga successiva, se possibile, ma il controllo non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="aa86d-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa86d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa86d-108">See Also</span></span>  
 [<span data-ttu-id="aa86d-109">Procedura: Creare tasti di scelta con i controlli Label di Windows Form</span><span class="sxs-lookup"><span data-stu-id="aa86d-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [<span data-ttu-id="aa86d-110">Panoramica sul controllo Label</span><span class="sxs-lookup"><span data-stu-id="aa86d-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="aa86d-111">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="aa86d-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
