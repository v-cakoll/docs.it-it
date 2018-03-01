---
title: 'Procedura: eseguire operazioni di trascinamento e rilascio tra applicazioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 514c283575ca54e74d23ae31d3590979be2c3ef0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="a55f7-102">Procedura: eseguire operazioni di trascinamento e rilascio tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="a55f7-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="a55f7-103">Eseguire operazioni di trascinamento della selezione tra applicazioni non è diverso dal consentire quest'azione nell'ambito di un'applicazione, purché entrambe le applicazioni implicate si comportino in base al "contratto" stabilito tra le proprietà <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> e <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="a55f7-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="a55f7-104">Nella procedura seguente si userà un'applicazione basata su Windows creata dall'utente e l'elaboratore di testi WordPad incluso con il sistema operativo Windows per eseguire operazioni di trascinamento della selezione tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a55f7-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="a55f7-105">WordPad offre un determinato set di effetti consentiti per il trascinamento del testo selezionato; l'applicazione basata su Windows per cui si scriverà il codice interagirà con tali effetti, in modo che le operazioni di trascinamento della selezione possano essere completate correttamente.</span><span class="sxs-lookup"><span data-stu-id="a55f7-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="a55f7-106">Per eseguire una procedura di trascinamento della selezione tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="a55f7-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="a55f7-107">Creare una nuova applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a55f7-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="a55f7-108">Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="a55f7-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="a55f7-109">Configurare il controllo <xref:System.Windows.Forms.TextBox> per ricevere dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="a55f7-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="a55f7-110">Per ulteriori informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento e rilascio in Windows Form](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a55f7-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="a55f7-111">Eseguire l'applicazione basata su Windows e, mentre l'applicazione è in esecuzione, eseguire WordPad.</span><span class="sxs-lookup"><span data-stu-id="a55f7-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="a55f7-112">WordPad è un editor di testo installato da Windows che consente operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="a55f7-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="a55f7-113">È accessibile premendo il **avviare** pulsante, la selezione di **eseguire**e quindi digitando `WordPad` nella casella di testo del **eseguire** la finestra di dialogo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a55f7-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="a55f7-114">Una volta aperto WordPad, digitare una stringa di testo al suo interno.</span><span class="sxs-lookup"><span data-stu-id="a55f7-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="a55f7-115">Usando il mouse, selezionare il testo e quindi trascinarlo sul controllo <xref:System.Windows.Forms.TextBox> nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="a55f7-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="a55f7-116">Osservare che quando si passa il mouse sul controllo <xref:System.Windows.Forms.TextBox> (e, di conseguenza, si genera l'evento <xref:System.Windows.Forms.Control.DragEnter>), il cursore cambia ed è possibile rilasciare il testo selezionato sul controllo <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a55f7-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="a55f7-117">È anche possibile configurare il controllo <xref:System.Windows.Forms.TextBox> per consentire il trascinamento delle stringhe di testo in WordPad.</span><span class="sxs-lookup"><span data-stu-id="a55f7-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="a55f7-118">Per ulteriori informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento e rilascio in Windows Form](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a55f7-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55f7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a55f7-119">See Also</span></span>  
 [<span data-ttu-id="a55f7-120">Procedura: Aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="a55f7-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="a55f7-121">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="a55f7-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="a55f7-122">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)</span><span class="sxs-lookup"><span data-stu-id="a55f7-122">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)</span></span>
