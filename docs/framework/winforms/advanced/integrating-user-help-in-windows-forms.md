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
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942922"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="98762-102">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="98762-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="98762-103">Un aspetto essenziale, ma spesso trascurato, di creare applicazioni basate su Windows è il sistema di Guida in linea, poiché si tratta in cui gli utenti attivano per ottenere assistenza nei periodi di confusione.</span><span class="sxs-lookup"><span data-stu-id="98762-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="98762-104">Windows Forms supporta due tipi diversi di Guida in linea, fornito dal [sul componente HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="98762-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="98762-105">Il primo consiste nel fatto che punta all'utente a un file della Guida di HTML o 1 della Guida HTML. *x* o formato maggiore.</span><span class="sxs-lookup"><span data-stu-id="98762-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="98762-106">Il secondo può visualizzare breve "Che cos'è questa"-tipo di Guida sui singoli controlli; Ciò è particolarmente utile nelle finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="98762-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="98762-107">Entrambi i tipi di Guida in linea sono utilizzabile nello stesso form.</span><span class="sxs-lookup"><span data-stu-id="98762-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="98762-108">Inoltre, il [componente ToolTip](../controls/tooltip-component-windows-forms.md) può essere utilizzato per fornire una Guida per i controlli in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="98762-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98762-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="98762-109">In This Section</span></span>  
 [<span data-ttu-id="98762-110">Procedura: Visualizzare la Guida in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="98762-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="98762-111">Viene illustrato come utilizzare il `HelpProvider` componente per collegare i controlli per i file della Guida.</span><span class="sxs-lookup"><span data-stu-id="98762-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="98762-112">Procedura: Visualizzare la Guida rapida</span><span class="sxs-lookup"><span data-stu-id="98762-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="98762-113">Viene illustrato come utilizzare il `HelpProvider` componente per visualizzare la Guida rapida su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="98762-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="98762-114">Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi</span><span class="sxs-lookup"><span data-stu-id="98762-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="98762-115">Viene descritto l'utilizzo di `ToolTip` componente per visualizzare la Guida specifica del controllo.</span><span class="sxs-lookup"><span data-stu-id="98762-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="98762-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="98762-116">Related Sections</span></span>  
 [<span data-ttu-id="98762-117">Componente HelpProvider</span><span class="sxs-lookup"><span data-stu-id="98762-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="98762-118">Illustra le nozioni di base di `HelpProvider` componente.</span><span class="sxs-lookup"><span data-stu-id="98762-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="98762-119">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="98762-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="98762-120">Illustra le nozioni di base di `ToolTip` componente.</span><span class="sxs-lookup"><span data-stu-id="98762-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="98762-121">Panoramica sui Windows Form</span><span class="sxs-lookup"><span data-stu-id="98762-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="98762-122">Illustra le nozioni di base di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="98762-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="98762-123">Windows Form</span><span class="sxs-lookup"><span data-stu-id="98762-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="98762-124">Viene fornita una panoramica di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="98762-124">Provides an overview of Windows Forms.</span></span>
