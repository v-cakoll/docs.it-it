---
title: 'Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: f9e7fad1f8b2b4e962f46a1e32522f47f01de2b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191874"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="9831a-102">Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="9831a-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="9831a-103">I moduli di Windows <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o può ridimensionare automaticamente in base alla lunghezza della didascalia.</span><span class="sxs-lookup"><span data-stu-id="9831a-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="9831a-104">Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie ingrandire o ridurre, che risulta particolarmente utile se la didascalia verrà modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9831a-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="9831a-105">Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto</span><span class="sxs-lookup"><span data-stu-id="9831a-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="9831a-106">Impostare relativi <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="9831a-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="9831a-107">Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostata su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà andrà a capo nella riga successiva, se possibile, ma il controllo non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="9831a-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9831a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9831a-108">See also</span></span>

- [<span data-ttu-id="9831a-109">Procedura: Creare tasti di scelta con i controlli Label di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9831a-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="9831a-110">Panoramica del controllo Label</span><span class="sxs-lookup"><span data-stu-id="9831a-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="9831a-111">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="9831a-111">Label Control</span></span>](label-control-windows-forms.md)
