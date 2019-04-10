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
ms.openlocfilehash: 110aab0c0826bb4b06e22158afd6af37b5406be4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312189"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="60172-102">Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="60172-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="60172-103">I moduli di Windows <xref:System.Windows.Forms.Label> controllo può essere a riga singola o multilinea e dimensioni fisse o può ridimensionare automaticamente in base alla lunghezza della didascalia.</span><span class="sxs-lookup"><span data-stu-id="60172-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="60172-104">Il <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà consente di ridimensionare i controlli per adattarli didascalie ingrandire o ridurre, che risulta particolarmente utile se la didascalia verrà modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60172-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="60172-105">Per rendere un controllo etichetta ridimensioni dinamicamente per adattarsi al contenuto</span><span class="sxs-lookup"><span data-stu-id="60172-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="60172-106">Impostare relativi <xref:System.Windows.Forms.Label.AutoSize%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="60172-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="60172-107">Se <xref:System.Windows.Forms.Label.AutoSize%2A> è impostata su `false`, le parole specificate nel <xref:System.Windows.Forms.Label.Text%2A> proprietà andrà a capo nella riga successiva, se possibile, ma il controllo non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="60172-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60172-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60172-108">See also</span></span>

- [<span data-ttu-id="60172-109">Procedura: Creare tasti di scelta con i controlli Label di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60172-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="60172-110">Panoramica del controllo Label</span><span class="sxs-lookup"><span data-stu-id="60172-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="60172-111">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="60172-111">Label Control</span></span>](label-control-windows-forms.md)
