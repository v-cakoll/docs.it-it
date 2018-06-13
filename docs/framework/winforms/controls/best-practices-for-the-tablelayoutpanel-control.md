---
title: Suggerimenti per il controllo TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526453"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="1d1bf-102">Suggerimenti per il controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="1d1bf-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="1d1bf-103">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce potenti funzioni di layout che è necessario considerare con attenzione prima di usare in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="1d1bf-104">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="1d1bf-104">Recommendations</span></span>  
 <span data-ttu-id="1d1bf-105">I suggerimenti seguenti consentono di utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllo relativo ottimale.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="1d1bf-106">Utilizzo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1d1bf-106">Targeted Use</span></span>  
 <span data-ttu-id="1d1bf-107">Utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllare con cautela.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="1d1bf-108">È consigliabile non utilizzare in tutte le situazioni che richiedono un layout ridimensionabile.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="1d1bf-109">Nell'elenco seguente vengono descritti i layout che traggono dall'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:</span><span class="sxs-lookup"><span data-stu-id="1d1bf-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="1d1bf-110">Layout in cui sono presenti più parti del form di ridimensionare in modo proporzionale a altro.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="1d1bf-111">Layout che verrà generato in modo dinamico in fase di esecuzione, ad esempio moduli di immissione dati che dispongono di campi personalizzabili aggiunte o sottratte o modificati in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="1d1bf-112">Layout che deve rimanere in una dimensione fissa globale.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="1d1bf-113">Ad esempio, potrebbe essere una finestra di dialogo che deve rimanere inferiore a 800 x 600, ma è necessario supportare le stringhe localizzate.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="1d1bf-114">Nell'elenco seguente vengono descritti i layout che non traggono dall'utilizzo di <xref:System.Windows.Forms.TableLayoutPanel> controllo:</span><span class="sxs-lookup"><span data-stu-id="1d1bf-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="1d1bf-115">Semplice moduli di immissione dati con una singola colonna di etichette e una singola colonna di aree di immissione di testo.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="1d1bf-116">Form con un unico grande Visualizza l'area che deve occupare tutto lo spazio disponibile quando si verifica un ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="1d1bf-117">Un esempio di questo è un modulo che consente di visualizzare un singolo <xref:System.Windows.Forms.PropertyGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="1d1bf-118">In questo caso, utilizzare l'ancoraggio perché nessun altro elemento deve espandere quando il form viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="1d1bf-119">Scegliere con attenzione i controlli che devono essere un <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="1d1bf-120">Se si dispone di spazio per il testo per l'aumento delle dimensioni del 30% tramite ancoraggio, è consigliabile utilizzare il <xref:System.Windows.Forms.Control.Anchor%2A> solo per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="1d1bf-121">Se è possibile stimare lo spazio richiesto dal layout, consente di <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> anziché stimare i dettagli dello spazio rimanente e <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="1d1bf-122">In generale, quando si progetta il layout con il <xref:System.Windows.Forms.TableLayoutPanel> di controllo, semplificare la progettazione.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="1d1bf-123">Utilizzare la finestra Struttura documento</span><span class="sxs-lookup"><span data-stu-id="1d1bf-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="1d1bf-124">La finestra Struttura documento offre una visualizzazione albero di layout, che è possibile utilizzare per modificare le relazioni padre-figlio e di ordine z dei controlli.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="1d1bf-125">Dal **dal menu Visualizza**selezionare **altre finestre**, quindi selezionare **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="1d1bf-126">Evitare l'annidamento</span><span class="sxs-lookup"><span data-stu-id="1d1bf-126">Avoid Nesting</span></span>  
 <span data-ttu-id="1d1bf-127">Evitare di annidare altri <xref:System.Windows.Forms.TableLayoutPanel> controlli all'interno di un <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="1d1bf-128">Può essere difficile il debug di layout nidificati.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="1d1bf-129">Evitare l'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="1d1bf-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="1d1bf-130">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo non supporta l'ereditarietà visiva in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="1d1bf-131">Oggetto <xref:System.Windows.Forms.TableLayoutPanel> come "bloccato" in fase di progettazione verrà visualizzato un controllo in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1d1bf-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d1bf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d1bf-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
