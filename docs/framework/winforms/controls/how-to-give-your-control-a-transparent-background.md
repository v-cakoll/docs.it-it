---
title: 'Procedura: Assegnare al controllo uno sfondo trasparente'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 5a54b76eb92c7d3f518b9bf13e154e6faf58de63
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718168"
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Procedura: Assegnare al controllo uno sfondo trasparente
Nelle versioni precedenti di .NET Framework, i controlli non supportavano gli sfondi trasparenti senza aver prima impostato il metodo <xref:System.Windows.Forms.Control.SetStyle%2A> nel costruttore del modulo. Nella versione corrente del framework è possibile impostare il colore di sfondo per la maggior parte dei controlli su <xref:System.Drawing.Color.Transparent%2A> nella finestra **Proprietà** in fase di progettazione o nel codice nel costruttore del modulo.  
  
> [!NOTE]
>  I controlli Windows Form non supportano la trasparenza vera e propria. Lo sfondo di un controllo Windows Form trasparente viene disegnato dal relativo padre.  
  
> [!NOTE]
>  Il controllo <xref:System.Windows.Controls.Button> non supporta uno sfondo trasparente neanche quando la proprietà <xref:System.Windows.Forms.ButtonBase.BackColor%2A> è impostata su <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Per assegnare al controllo uno sfondo trasparente  
  
-   Nella finestra Proprietà scegliere la proprietà <xref:System.Windows.Forms.ButtonBase.BackColor%2A> e impostarla su <xref:System.Drawing.Color.Transparent%2A>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Color.FromArgb%2A>
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
- [Uso di classi grafiche gestite](../advanced/using-managed-graphics-classes.md)
- [Procedura: Disegnare linee opache e semitrasparenti](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
