---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717446"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="3454c-102">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="3454c-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="3454c-103">Le applicazioni di interfaccia a documenti multipli (MDI) consentono di visualizzare documenti multipli nello stesso momento, con ogni documento visualizzato in una finestra.</span><span class="sxs-lookup"><span data-stu-id="3454c-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="3454c-104">Le applicazioni MDI hanno spesso una voce di menu finestra con sottomenu per lo spostamento tra finestre e documenti.</span><span class="sxs-lookup"><span data-stu-id="3454c-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3454c-105">Esistono alcune differenze di comportamento tra i form MDI e interfaccia a documento singolo (SDI) windows in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3454c-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="3454c-106">Il `Opacity` proprietà non influiscono sull'aspetto del form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="3454c-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="3454c-107">Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> (metodo) non influiscono sul comportamento dei form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="3454c-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3454c-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3454c-108">In This Section</span></span>  
 [<span data-ttu-id="3454c-109">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="3454c-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="3454c-110">Fornisce indicazioni per la creazione del contenitore per più documenti all'interno di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="3454c-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="3454c-111">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="3454c-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="3454c-112">Vengono fornite indicazioni per la creazione di una o più finestre usate all'interno di un form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="3454c-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="3454c-113">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="3454c-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="3454c-114">Fornisce indicazioni per la verifica per determinare se la finestra figlio con lo stato attivo (e invia il contenuto negli Appunti).</span><span class="sxs-lookup"><span data-stu-id="3454c-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="3454c-115">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="3454c-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="3454c-116">Fornisce indicazioni per il trasferimento delle informazioni alla finestra figlio attiva.</span><span class="sxs-lookup"><span data-stu-id="3454c-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="3454c-117">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="3454c-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="3454c-118">Vengono fornite indicazioni per l'affiancamento, CSS o disporre le finestre figlio di un'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="3454c-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
