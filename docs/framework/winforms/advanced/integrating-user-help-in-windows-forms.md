---
title: Integrazione della Guida dell'utente in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: b16ba14eea68083cd7bdfc91c88375406137f450
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527223"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="08f76-102">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="08f76-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="08f76-103">Un aspetto fondamentale, ma spesso trascurato, di compilazione di applicazioni basate su Windows è il sistema di Guida in linea, che viene in cui gli utenti per assistenza nell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="08f76-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="08f76-104">Windows Form supportano due diversi tipi di Guida, fornito dal [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="08f76-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="08f76-105">Il primo prevede la visualizzazione di un file della Guida HTML o HTML Help 1. *x* o successiva.</span><span class="sxs-lookup"><span data-stu-id="08f76-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="08f76-106">Il secondo può visualizzare breve "Che cos'è questa"-digitare Help sui singoli controlli; Ciò è particolarmente utile nelle finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="08f76-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="08f76-107">Entrambi i tipi di Guida utilizzabile nello stesso form.</span><span class="sxs-lookup"><span data-stu-id="08f76-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="08f76-108">Inoltre, il [componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) può essere usato per fornire una Guida per i controlli in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="08f76-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08f76-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="08f76-109">In This Section</span></span>  
 [<span data-ttu-id="08f76-110">Procedura: Visualizzare la Guida in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="08f76-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="08f76-111">Viene illustrato come utilizzare il `HelpProvider` componente per collegare i controlli per i file della Guida.</span><span class="sxs-lookup"><span data-stu-id="08f76-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="08f76-112">Procedura: Visualizzare la Guida rapida</span><span class="sxs-lookup"><span data-stu-id="08f76-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="08f76-113">Viene illustrato come utilizzare il `HelpProvider` componente per visualizzare la Guida rapida in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="08f76-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="08f76-114">Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi</span><span class="sxs-lookup"><span data-stu-id="08f76-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="08f76-115">Viene descritto l'utilizzo di `ToolTip` componente per visualizzare la Guida specifica del controllo.</span><span class="sxs-lookup"><span data-stu-id="08f76-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08f76-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="08f76-116">Related Sections</span></span>  
 [<span data-ttu-id="08f76-117">Componente HelpProvider</span><span class="sxs-lookup"><span data-stu-id="08f76-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="08f76-118">Illustra le nozioni di base di `HelpProvider` componente.</span><span class="sxs-lookup"><span data-stu-id="08f76-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="08f76-119">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="08f76-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="08f76-120">Illustra le nozioni di base di `ToolTip` componente.</span><span class="sxs-lookup"><span data-stu-id="08f76-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="08f76-121">Panoramica sui Windows Form</span><span class="sxs-lookup"><span data-stu-id="08f76-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="08f76-122">Illustra le nozioni di base di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="08f76-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="08f76-123">Windows Form</span><span class="sxs-lookup"><span data-stu-id="08f76-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="08f76-124">Viene fornita una panoramica di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="08f76-124">Provides an overview of Windows Forms.</span></span>
