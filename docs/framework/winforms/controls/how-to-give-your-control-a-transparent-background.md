---
title: 'Procedura: Assegnare uno sfondo trasparente al controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 671075973793d7fbf0b70ce77428a0a632305b9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206096"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="f057e-102">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="f057e-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="f057e-103">Nelle versioni precedenti di .NET Framework, i controlli non supportavano gli sfondi trasparenti senza aver prima impostato il metodo <xref:System.Windows.Forms.Control.SetStyle%2A> nel costruttore del modulo.</span><span class="sxs-lookup"><span data-stu-id="f057e-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="f057e-104">Nella versione corrente del framework è possibile impostare il colore di sfondo per la maggior parte dei controlli su <xref:System.Drawing.Color.Transparent%2A> nella finestra **Proprietà** in fase di progettazione o nel codice nel costruttore del modulo.</span><span class="sxs-lookup"><span data-stu-id="f057e-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f057e-105">I controlli Windows Form non supportano la trasparenza vera e propria.</span><span class="sxs-lookup"><span data-stu-id="f057e-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="f057e-106">Lo sfondo di un controllo Windows Form trasparente viene disegnato dal relativo padre.</span><span class="sxs-lookup"><span data-stu-id="f057e-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f057e-107">Il controllo <xref:System.Windows.Controls.Button> non supporta uno sfondo trasparente neanche quando la proprietà <xref:System.Windows.Forms.ButtonBase.BackColor%2A> è impostata su <xref:System.Drawing.Color.Transparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="f057e-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="f057e-108">Per assegnare al controllo uno sfondo trasparente</span><span class="sxs-lookup"><span data-stu-id="f057e-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="f057e-109">Nella finestra Proprietà scegliere il <xref:System.Windows.Forms.ButtonBase.BackColor%2A> proprietà e impostarla su</span><span class="sxs-lookup"><span data-stu-id="f057e-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to</span></span> <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a><span data-ttu-id="f057e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f057e-110">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="f057e-111">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f057e-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="f057e-112">Utilizzo di classi grafiche gestite</span><span class="sxs-lookup"><span data-stu-id="f057e-112">Using Managed Graphics Classes</span></span>](../advanced/using-managed-graphics-classes.md)
- [<span data-ttu-id="f057e-113">Procedura: Disegnare linee opache e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="f057e-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
