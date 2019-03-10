---
title: 'Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 5771b232d77e3e5a792b179ebffd3fa0edda7c9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702194"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="c65d2-102">Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="c65d2-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="c65d2-103">I moduli di Windows <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o può ridimensionare automaticamente in base alla lunghezza della didascalia.</span><span class="sxs-lookup"><span data-stu-id="c65d2-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="c65d2-104">Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie ingrandire o ridurre, che risulta particolarmente utile se la didascalia verrà modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c65d2-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="c65d2-105">Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto</span><span class="sxs-lookup"><span data-stu-id="c65d2-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="c65d2-106">Impostare relativi <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="c65d2-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="c65d2-107">Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostata su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà andrà a capo nella riga successiva, se possibile, ma il controllo non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="c65d2-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65d2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c65d2-108">See also</span></span>
- [<span data-ttu-id="c65d2-109">Procedura: Creare le chiavi di accesso con i controlli Label di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c65d2-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="c65d2-110">Panoramica sul controllo Label</span><span class="sxs-lookup"><span data-stu-id="c65d2-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="c65d2-111">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="c65d2-111">Label Control</span></span>](label-control-windows-forms.md)
