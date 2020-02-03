---
title: Ridimensionare un controllo Label per adattarne il contenuto
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743779"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="9e652-102">Procedura: ridimensionare un controllo Label Windows Form in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="9e652-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="9e652-103">Il Windows Forms controllo <xref:System.Windows.Forms.Label> può essere a riga singola o a più righe e può essere a dimensione fissa oppure può ridimensionarsi automaticamente per adattarlo alla didascalia.</span><span class="sxs-lookup"><span data-stu-id="9e652-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="9e652-104">Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli a didascalie più grandi o più piccole, operazione particolarmente utile se la didascalia cambierà in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9e652-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="9e652-105">Per ridimensionare dinamicamente il controllo etichetta per adattarlo al contenuto</span><span class="sxs-lookup"><span data-stu-id="9e652-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="9e652-106">Impostarne la proprietà <xref:System.Windows.Forms.Label.AutoSize%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="9e652-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="9e652-107">Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostato su `false`, le parole specificate nella proprietà <xref:System.Windows.Forms.Label.Text%2A> verrà eseguito il wrapping alla riga successiva, se possibile, ma il controllo non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="9e652-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e652-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e652-108">See also</span></span>

- [<span data-ttu-id="9e652-109">Procedura: Creare tasti di scelta con i controlli Label di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9e652-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="9e652-110">Panoramica sul controllo Label</span><span class="sxs-lookup"><span data-stu-id="9e652-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="9e652-111">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="9e652-111">Label Control</span></span>](label-control-windows-forms.md)
