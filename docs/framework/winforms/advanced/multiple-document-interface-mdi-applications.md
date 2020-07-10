---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
description: Informazioni su come Windows Forms le applicazioni con interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti contemporaneamente, con ogni documento visualizzato in una finestra.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174653"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="7bf9b-103">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="7bf9b-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="7bf9b-104">Le applicazioni con interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti contemporaneamente, con ogni documento visualizzato in una finestra.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="7bf9b-105">Le applicazioni MDI spesso dispongono di una voce di menu finestra con sottomenu per passare da una finestra all'altra o da documenti.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bf9b-106">Esistono alcune differenze di comportamento tra i form MDI e le finestre di interfaccia a documento singolo (SDI) in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="7bf9b-107">La `Opacity` proprietà non influisce sull'aspetto dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="7bf9b-108">Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> metodo non influisce sul comportamento dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bf9b-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7bf9b-109">In This Section</span></span>  
 [<span data-ttu-id="7bf9b-110">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="7bf9b-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="7bf9b-111">Fornisce indicazioni per la creazione del contenitore per più documenti all'interno di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="7bf9b-112">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="7bf9b-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="7bf9b-113">Fornisce indicazioni per la creazione di una o più finestre che operano all'interno di un form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="7bf9b-114">Procedura: determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="7bf9b-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="7bf9b-115">Fornisce indicazioni per verificare la finestra figlio con lo stato attivo (e inviarne il contenuto agli Appunti).</span><span class="sxs-lookup"><span data-stu-id="7bf9b-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="7bf9b-116">Procedura: inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="7bf9b-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="7bf9b-117">Fornisce indicazioni per il trasporto delle informazioni nella finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="7bf9b-118">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="7bf9b-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="7bf9b-119">Fornisce indicazioni per l'affiancamento, la propagazione o la disposizione delle finestre figlio di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="7bf9b-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
