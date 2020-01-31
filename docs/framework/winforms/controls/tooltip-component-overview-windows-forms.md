---
title: Cenni preliminari sul componente ToolTip
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741912"
---
# <a name="tooltip-component-overview-windows-forms"></a>Cenni preliminari sul componente ToolTip (Windows Form)
Il componente <xref:System.Windows.Forms.ToolTip> di Windows Form visualizza un testo quando l'utente posiziona il puntatore sui controlli. Una descrizione comando può essere associata a qualsiasi controllo. Esempio di utilizzo di questo componente: per risparmiare spazio in un form, è possibile visualizzare un'icona di piccole dimensioni su un pulsante e utilizzare una descrizione comando per spiegare la funzione del pulsante.  
  
## <a name="working-with-the-tooltip-component"></a>Utilizzo del componente descrizione comando  
 Un componente <xref:System.Windows.Forms.ToolTip> fornisce una proprietà `ToolTip` a più controlli in un Windows Form o in un altro contenitore. Se ad esempio si inserisce un componente <xref:System.Windows.Forms.ToolTip> in un modulo, è possibile visualizzare "digitare il nome per un controllo <xref:System.Windows.Forms.TextBox> e" fare clic qui per salvare le modifiche "per un controllo di <xref:System.Windows.Forms.Button>.  
  
 I metodi chiave del componente <xref:System.Windows.Forms.ToolTip> sono <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> e <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. È possibile usare il metodo <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> per impostare le descrizioni comandi visualizzate per i controlli. Per altre informazioni, vedere [procedura: impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Le proprietà chiave sono <xref:System.Windows.Forms.ToolTip.Active%2A>, che devono essere impostate su `true` per visualizzare la descrizione comando e <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, che consente di impostare l'intervallo di tempo in cui viene visualizzata la stringa della descrizione comando, per quanto tempo l'utente deve puntare al controllo affinché venga visualizzata la descrizione comando e il tempo necessario per la visualizzazione delle finestre di descrizione comando successive. Per altre informazioni, vedere [How to: Change the delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolTip>
- [Procedura: Impostare le descrizioni comandi per i controlli in un Windows Form in fase di progettazione](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Procedura: Modifica del ritardo del componente ToolTip di Windows Form](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
