---
title: 'Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015755"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="09db9-102">Procedura dettagliata: Eseguire attività comuni usando gli smart tag</span><span class="sxs-lookup"><span data-stu-id="09db9-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="09db9-103">Quando si costruiscono moduli e controlli per la Windows Forms Application, è possibile eseguire ripetutamente diverse attività.</span><span class="sxs-lookup"><span data-stu-id="09db9-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="09db9-104">Di seguito sono riportate alcune delle attività comunemente eseguite che si verificheranno:</span><span class="sxs-lookup"><span data-stu-id="09db9-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="09db9-105">Aggiunta o rimozione di una scheda in <xref:System.Windows.Forms.TabControl>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="09db9-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="09db9-106">Ancoraggio di un controllo al relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="09db9-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="09db9-107">Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="09db9-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="09db9-108">Per velocizzare lo sviluppo, molti controlli offrono smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="09db9-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="09db9-109">Queste attività sono denominate *verbi smart tag*.</span><span class="sxs-lookup"><span data-stu-id="09db9-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="09db9-110">Gli smart tag rimangono collegati a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="09db9-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="09db9-111">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="09db9-111">Create the project</span></span>

<span data-ttu-id="09db9-112">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="09db9-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="09db9-113">In Visual Studio creare un progetto di applicazione basato su Windows denominato **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="09db9-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="09db9-114">Selezionare il modulo nella **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="09db9-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="09db9-115">Usa Smart Tag</span><span class="sxs-lookup"><span data-stu-id="09db9-115">Use smart tags</span></span>

<span data-ttu-id="09db9-116">Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che li offrono.</span><span class="sxs-lookup"><span data-stu-id="09db9-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="09db9-117">Trascinare un <xref:System.Windows.Forms.TabControl> oggetto dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="09db9-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="09db9-118">Si noti il glifo smart tag (![glifo](./media/vs-winformsmttagglyph.gif)smart tag) che viene visualizzato <xref:System.Windows.Forms.TabControl>sul lato della.</span><span class="sxs-lookup"><span data-stu-id="09db9-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="09db9-119">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="09db9-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="09db9-120">Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** .</span><span class="sxs-lookup"><span data-stu-id="09db9-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="09db9-121">Osservare che viene aggiunta una nuova scheda a <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="09db9-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="09db9-122">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="09db9-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="09db9-123">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="09db9-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="09db9-124">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** .</span><span class="sxs-lookup"><span data-stu-id="09db9-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="09db9-125">Osservare che una nuova colonna viene aggiunta al <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="09db9-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="09db9-126">Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="09db9-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="09db9-127">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="09db9-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="09db9-128">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** .</span><span class="sxs-lookup"><span data-stu-id="09db9-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="09db9-129">Osservare che la <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è ora orientata orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="09db9-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="09db9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09db9-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
