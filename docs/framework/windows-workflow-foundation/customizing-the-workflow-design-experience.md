---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 2d6ef24d00baa4df6dfc8e0af69c1d489b79a41f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945990"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="c91c1-102">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c91c1-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="c91c1-103">In [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] sono stati semplificati gli scenari per progettare le attività personalizzate e riallocare [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c91c1-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="c91c1-104">Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili.</span><span class="sxs-lookup"><span data-stu-id="c91c1-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="c91c1-105">La modifica infrastrutturale principale prevede che il nuovo modello di programmazione della finestra di progettazione attività viene compilato su Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c91c1-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c91c1-106">In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in altre applicazioni in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="c91c1-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="c91c1-107">In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato.</span><span class="sxs-lookup"><span data-stu-id="c91c1-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="c91c1-108">L'integrazione con Windows Communication Foundation (WCF) è diventato più semplice grazie all'uso dei servizi del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c91c1-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="c91c1-109">Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.</span><span class="sxs-lookup"><span data-stu-id="c91c1-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c91c1-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c91c1-110">In This Section</span></span>

 [<span data-ttu-id="c91c1-111">Uso di finestre di progettazione e modelli di attività personalizzati</span><span class="sxs-lookup"><span data-stu-id="c91c1-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="c91c1-112">Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c91c1-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="c91c1-113">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="c91c1-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="c91c1-114">Viene descritto come riallocare la [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] all'esterno di Visual Studio e come visualizzare gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="c91c1-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="c91c1-115">Uso di un editor di espressioni personalizzato</span><span class="sxs-lookup"><span data-stu-id="c91c1-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="c91c1-116">Viene descritto come implementare un editor di espressioni personalizzato da usare con le finestre di progettazione del flusso di lavoro riallocate all'esterno di Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="c91c1-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="c91c1-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c91c1-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="c91c1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c91c1-118">See also</span></span>

- [<span data-ttu-id="c91c1-119">Estensione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="c91c1-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="c91c1-120">Finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="c91c1-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="c91c1-121">ActivityDesigner personalizzati</span><span class="sxs-lookup"><span data-stu-id="c91c1-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="c91c1-122">Riallocazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="c91c1-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)