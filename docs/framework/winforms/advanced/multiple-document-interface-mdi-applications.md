---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956552"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="0b436-102">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="0b436-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="0b436-103">Le applicazioni con interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti contemporaneamente, con ogni documento visualizzato in una finestra.</span><span class="sxs-lookup"><span data-stu-id="0b436-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="0b436-104">Le applicazioni MDI spesso dispongono di una voce di menu finestra con sottomenu per passare da una finestra all'altra o da documenti.</span><span class="sxs-lookup"><span data-stu-id="0b436-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b436-105">Esistono alcune differenze di comportamento tra i form MDI e le finestre di interfaccia a documento singolo (SDI) in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0b436-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="0b436-106">La `Opacity` proprietà non influisce sull'aspetto dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="0b436-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="0b436-107">Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> metodo non influisce sul comportamento dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="0b436-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b436-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0b436-108">In This Section</span></span>  
 [<span data-ttu-id="0b436-109">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="0b436-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="0b436-110">Fornisce indicazioni per la creazione del contenitore per più documenti all'interno di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="0b436-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="0b436-111">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0b436-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="0b436-112">Fornisce indicazioni per la creazione di una o più finestre che operano all'interno di un form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="0b436-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="0b436-113">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0b436-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="0b436-114">Fornisce indicazioni per verificare la finestra figlio con lo stato attivo (e inviarne il contenuto agli Appunti).</span><span class="sxs-lookup"><span data-stu-id="0b436-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="0b436-115">Procedura: Invia dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0b436-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="0b436-116">Fornisce indicazioni per il trasporto delle informazioni nella finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="0b436-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="0b436-117">Procedura: Disponi form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0b436-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="0b436-118">Fornisce indicazioni per l'affiancamento, la propagazione o la disposizione delle finestre figlio di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="0b436-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
