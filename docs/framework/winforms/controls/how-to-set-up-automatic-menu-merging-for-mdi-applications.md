---
title: 'Procedura: impostare l''unione automatica dei menu per applicazioni MDI'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="7d2f6-102">Procedura: impostare l'unione automatica dei menu per applicazioni MDI</span><span class="sxs-lookup"><span data-stu-id="7d2f6-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="7d2f6-103">La procedura seguente fornisce i passaggi di base per la configurazione di unione automatica in un'applicazione con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="7d2f6-104">Per impostare l'unione automatica dei menu</span><span class="sxs-lookup"><span data-stu-id="7d2f6-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="7d2f6-105">Creare il form padre MDI impostando il relativo <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="7d2f6-106">Aggiungere un <xref:System.Windows.Forms.MenuStrip> il padre MDI, impostando il relativo <xref:System.Windows.Forms.Form.MainMenuStrip%2A> che proprietà <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="7d2f6-107">Creare un form figlio MDI e impostare il relativo <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="7d2f6-108">Aggiungere un <xref:System.Windows.Forms.MenuStrip> per il form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="7d2f6-109">Nel form figlio, impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà del <xref:System.Windows.Forms.MenuStrip> a `false`.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="7d2f6-110">Aggiungere le voci di menu del form figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire il form padre <xref:System.Windows.Forms.MenuStrip> quando è attivato il form figlio.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="7d2f6-111">Utilizzare il <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà dal menu di elementi del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di unione nel form padre.</span><span class="sxs-lookup"><span data-stu-id="7d2f6-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2f6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d2f6-112">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="7d2f6-113">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7d2f6-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
