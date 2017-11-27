---
title: "Procedura dettagliata: esecuzione di attività comuni utilizzando gli smart tag nei controlli Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2e6b815be85576f037e0f24668c44756b95abd6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="a061b-102">Procedura dettagliata: esecuzione di attività comuni utilizzando gli smart tag nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="a061b-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="a061b-103">Come si creano i form e controlli per l'applicazione Windows Form, sono disponibili numerose attività che verranno eseguite più volte.</span><span class="sxs-lookup"><span data-stu-id="a061b-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="a061b-104">Queste sono alcune delle attività comunemente svolte che si verificheranno:</span><span class="sxs-lookup"><span data-stu-id="a061b-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="a061b-105">Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a061b-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="a061b-106">Ancoraggio di un controllo al relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="a061b-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="a061b-107">Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="a061b-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="a061b-108">Per velocizzare lo sviluppo, molti controlli offrono gli smart tag sono menu sensibile al contesto che consentono di eseguire attività comuni come in un singolo movimento in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a061b-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="a061b-109">Queste attività vengono chiamate *verbi di smart tag*.</span><span class="sxs-lookup"><span data-stu-id="a061b-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="a061b-110">Gli smart tag rimanere connessi a un'istanza di controllo per la relativa durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="a061b-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="a061b-111">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="a061b-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="a061b-112">Creazione di un progetto Windows Form</span><span class="sxs-lookup"><span data-stu-id="a061b-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="a061b-113">Utilizzando gli smart tag</span><span class="sxs-lookup"><span data-stu-id="a061b-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="a061b-114">Abilitazione e disabilitazione Smart tag</span><span class="sxs-lookup"><span data-stu-id="a061b-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="a061b-115">Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.</span><span class="sxs-lookup"><span data-stu-id="a061b-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a061b-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="a061b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a061b-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a061b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a061b-118">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a061b-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="a061b-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="a061b-119">Creating the Project</span></span>  
 <span data-ttu-id="a061b-120">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="a061b-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="a061b-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="a061b-121">To create the project</span></span>  
  
1.  <span data-ttu-id="a061b-122">Creare un progetto di applicazione basata su Windows denominato "SmartTagsExample".</span><span class="sxs-lookup"><span data-stu-id="a061b-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="a061b-123">Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="a061b-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="a061b-124">Selezionare il form nel **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="a061b-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="a061b-125">Utilizzando gli Smart tag</span><span class="sxs-lookup"><span data-stu-id="a061b-125">Using Smart Tags</span></span>  
 <span data-ttu-id="a061b-126">Gli smart tag sono sempre disponibili in fase di progettazione per controlli quali sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="a061b-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="a061b-127">Utilizzo di smart tag</span><span class="sxs-lookup"><span data-stu-id="a061b-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="a061b-128">Trascinare un <xref:System.Windows.Forms.TabControl> dal **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="a061b-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="a061b-129">Si noti il glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) che viene visualizzato sul lato del <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a061b-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="a061b-130">Fare clic sull'icona di smart tag.</span><span class="sxs-lookup"><span data-stu-id="a061b-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="a061b-131">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **Aggiungi scheda** elemento.</span><span class="sxs-lookup"><span data-stu-id="a061b-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="a061b-132">Si osservi che una nuova pagina della scheda viene aggiunta per il <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a061b-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="a061b-133">Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="a061b-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="a061b-134">Fare clic sull'icona di smart tag.</span><span class="sxs-lookup"><span data-stu-id="a061b-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="a061b-135">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **Aggiungi colonna** elemento.</span><span class="sxs-lookup"><span data-stu-id="a061b-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="a061b-136">Osservare che viene aggiunta una nuova colonna per il <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="a061b-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="a061b-137">Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo il **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="a061b-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="a061b-138">Fare clic sull'icona di smart tag.</span><span class="sxs-lookup"><span data-stu-id="a061b-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="a061b-139">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **orientamento separatore orizzontale** elemento.</span><span class="sxs-lookup"><span data-stu-id="a061b-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="a061b-140">Osservare che il <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è orientato in orizzontale.</span><span class="sxs-lookup"><span data-stu-id="a061b-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a061b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a061b-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="a061b-142">Procedura dettagliata: Aggiunta di Smart tag in un componente di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a061b-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
