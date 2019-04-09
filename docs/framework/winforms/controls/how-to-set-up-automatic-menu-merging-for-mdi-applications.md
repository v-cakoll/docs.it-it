---
title: "Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli"
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 17edde6e3968823abc915eb5faed6d2751ed9393
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129356"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="8cd81-102">Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli</span><span class="sxs-lookup"><span data-stu-id="8cd81-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="8cd81-103">La procedura seguente contiene i passaggi di base per la configurazione di unione automatica in un'applicazione di interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="8cd81-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="8cd81-104">Per impostare l'unione automatica dei menu</span><span class="sxs-lookup"><span data-stu-id="8cd81-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="8cd81-105">Creare il form padre MDI impostando relativi <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="8cd81-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="8cd81-106">Aggiungere un <xref:System.Windows.Forms.MenuStrip> all'elemento padre MDI, l'impostazione relativa <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà a cui <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="8cd81-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="8cd81-107">Creare un form figlio MDI e impostare il <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.</span><span class="sxs-lookup"><span data-stu-id="8cd81-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="8cd81-108">Aggiungere un <xref:System.Windows.Forms.MenuStrip> per form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="8cd81-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="8cd81-109">Nel form figlio, impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> a `false`.</span><span class="sxs-lookup"><span data-stu-id="8cd81-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="8cd81-110">Aggiungere le voci di menu del modulo figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire il form padre <xref:System.Windows.Forms.MenuStrip> quando viene attivato il form figlio.</span><span class="sxs-lookup"><span data-stu-id="8cd81-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="8cd81-111">Usare la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> gli elementi proprietà dal menu del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di unione in form padre.</span><span class="sxs-lookup"><span data-stu-id="8cd81-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd81-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cd81-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="8cd81-113">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="8cd81-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
