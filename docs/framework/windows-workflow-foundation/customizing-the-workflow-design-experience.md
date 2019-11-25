---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141933"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="38ab9-102">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="38ab9-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="38ab9-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="38ab9-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="38ab9-104">Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili.</span><span class="sxs-lookup"><span data-stu-id="38ab9-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="38ab9-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="38ab9-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="38ab9-106">In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in altre applicazioni in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="38ab9-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="38ab9-107">In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato.</span><span class="sxs-lookup"><span data-stu-id="38ab9-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="38ab9-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span><span class="sxs-lookup"><span data-stu-id="38ab9-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="38ab9-109">Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.</span><span class="sxs-lookup"><span data-stu-id="38ab9-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="38ab9-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="38ab9-110">In This Section</span></span>

 [<span data-ttu-id="38ab9-111">Uso di finestre di progettazione e modelli di attività personalizzati</span><span class="sxs-lookup"><span data-stu-id="38ab9-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="38ab9-112">Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="38ab9-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="38ab9-113">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="38ab9-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="38ab9-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span><span class="sxs-lookup"><span data-stu-id="38ab9-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="38ab9-115">Uso di un editor di espressioni personalizzato</span><span class="sxs-lookup"><span data-stu-id="38ab9-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="38ab9-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="38ab9-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="38ab9-117">Reference</span><span class="sxs-lookup"><span data-stu-id="38ab9-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="38ab9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38ab9-118">See also</span></span>

- [<span data-ttu-id="38ab9-119">Estensione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="38ab9-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="38ab9-120">Finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="38ab9-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="38ab9-121">ActivityDesigner personalizzati</span><span class="sxs-lookup"><span data-stu-id="38ab9-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="38ab9-122">Riallocazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="38ab9-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
