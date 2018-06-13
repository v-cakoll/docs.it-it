---
title: 'Procedura: assegnare uno sfondo trasparente al controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: ad814c9179fd33955fe4df2666f8a47606bfbff0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531817"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Procedura: assegnare uno sfondo trasparente al controllo
Nelle versioni precedenti di .NET Framework, i controlli non supportavano gli sfondi trasparenti senza aver prima impostato il metodo <xref:System.Windows.Forms.Control.SetStyle%2A> nel costruttore del modulo. Nella versione corrente del framework è possibile impostare il colore di sfondo per la maggior parte dei controlli su <xref:System.Drawing.Color.Transparent%2A> nella finestra **Proprietà** in fase di progettazione o nel codice nel costruttore del modulo.  
  
> [!NOTE]
>  I controlli Windows Form non supportano la trasparenza vera e propria. Lo sfondo di un controllo Windows Form trasparente viene disegnato dal relativo padre.  
  
> [!NOTE]
>  Il controllo <xref:System.Windows.Controls.Button> non supporta uno sfondo trasparente neanche quando la proprietà <xref:System.Windows.Forms.ButtonBase.BackColor%2A> è impostata su <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Per assegnare al controllo uno sfondo trasparente  
  
-   Nella finestra Proprietà scegliere la proprietà <xref:System.Windows.Forms.ButtonBase.BackColor%2A> e impostarla su <xref:System.Drawing.Color.Transparent%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Uso di classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [Procedura: Disegnare linee opache e semitrasparenti](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
