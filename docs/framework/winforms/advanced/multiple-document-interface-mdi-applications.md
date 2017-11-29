---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c122931b0a00f487ddab07550913988462cfd50e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="0729e-102">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="0729e-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="0729e-103">Applicazioni di interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti allo stesso tempo, con ogni documento visualizzato in una finestra.</span><span class="sxs-lookup"><span data-stu-id="0729e-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="0729e-104">Le applicazioni MDI hanno spesso una voce di menu finestra con sottomenu per passare da windows o documenti.</span><span class="sxs-lookup"><span data-stu-id="0729e-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0729e-105">Esistono alcune differenze di comportamento tra form MDI e interfaccia a documento singolo (SDI) in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0729e-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="0729e-106">Il `Opacity` proprietà non influiscono sull'aspetto del form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="0729e-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="0729e-107">Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> (metodo) non influiscono sul comportamento dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="0729e-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0729e-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0729e-108">In This Section</span></span>  
 [<span data-ttu-id="0729e-109">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="0729e-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="0729e-110">Vengono fornite indicazioni per la creazione del contenitore di documenti multipli all'interno di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="0729e-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="0729e-111">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0729e-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="0729e-112">Vengono fornite indicazioni per la creazione di una o più finestre che funzionano all'interno di un form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="0729e-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="0729e-113">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0729e-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="0729e-114">Fornisce indicazioni per la verifica per determinare se la finestra figlio con stato attivo (e invio del relativo contenuto negli Appunti).</span><span class="sxs-lookup"><span data-stu-id="0729e-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="0729e-115">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0729e-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="0729e-116">Vengono fornite indicazioni per trasferire le informazioni alla finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="0729e-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="0729e-117">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0729e-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="0729e-118">Vengono fornite indicazioni per l'affiancamento, CSS o disporre le finestre figlio di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="0729e-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
