---
title: Controllo StatusBar (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 945d9a658dd3d75dd0edb9f4eaca78334ee4d652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="551a3-102">Controllo StatusBar (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="551a3-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="551a3-103">Benché il controllo <xref:System.Windows.Forms.ToolStripStatusLabel> sostituisca il controllo <xref:System.Windows.Forms.StatusBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.StatusBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="551a3-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="551a3-104">Il controllo <xref:System.Windows.Forms.StatusBar> di Windows Form viene usato nei form come un'area solitamente rappresentata nella parte inferiore di una finestra, in cui possono essere visualizzati diversi tipi di informazioni sullo stato di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="551a3-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="551a3-105"><xref:System.Windows.Forms.StatusBar>controlli possono disporre di pannelli della barra di stato in cui visualizzare le icone per indicare lo stato o una serie di icone per indicare che un processo è in corso; un'animazione ad esempio, Microsoft Word che indica che il documento viene salvato.</span><span class="sxs-lookup"><span data-stu-id="551a3-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="551a3-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="551a3-106">In This Section</span></span>  
 [<span data-ttu-id="551a3-107">Cenni preliminari sul controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="551a3-107">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="551a3-108">Introduce i concetti generali relativi il <xref:System.Windows.Forms.StatusBar> controllo, che consente agli utenti di visualizzare informazioni importanti per il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="551a3-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="551a3-109">Procedura: Aggiungere pannelli a un controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="551a3-109">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="551a3-110">Viene illustrato come aggiungere pannelli programmabili per il <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="551a3-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="551a3-111">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="551a3-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="551a3-112">Viene illustrato come gestire <xref:System.Windows.Forms.Control.Click> gli eventi generati dal <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="551a3-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="551a3-113">Procedura: Impostare la dimensione dei pannelli della barra di stato</span><span class="sxs-lookup"><span data-stu-id="551a3-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="551a3-114">Fornisce informazioni dettagliate sulle proprietà che controllano la larghezza e di ridimensionamento dei pannelli della barra di stato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="551a3-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="551a3-115">Procedura dettagliata: Aggiornamento delle informazioni sulla barra di stato in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="551a3-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="551a3-116">Viene illustrato come controllare a livello di programmazione i dati in altri pannelli della barra di stato.</span><span class="sxs-lookup"><span data-stu-id="551a3-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="551a3-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="551a3-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="551a3-118">Fornisce informazioni di riferimento sulla classe e sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="551a3-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="551a3-119">Sostituisce e aggiunge la funzionalità per il <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="551a3-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="551a3-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="551a3-120">Related Sections</span></span>  
 [<span data-ttu-id="551a3-121">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="551a3-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="551a3-122">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="551a3-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
