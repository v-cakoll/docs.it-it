---
title: 'Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bbf6bcf6550c17a514edb28eecbe8d5d74ba7af2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="4b8fc-102">Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata</span><span class="sxs-lookup"><span data-stu-id="4b8fc-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="4b8fc-103">In questo argomento viene descritto come recuperare e pubblicare errori di convalida in un [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] riallocato.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="4b8fc-104">Viene in tal modo fornita la procedura per confermare che un flusso di lavoro in una finestra di progettazione riallocata è valido.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="4b8fc-105">Questa attività dispone di due parti.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-105">This task has two parts.</span></span> <span data-ttu-id="4b8fc-106">La prima consiste nel fornire un'implementazione di <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="4b8fc-107">È disponibile metodo critico da implementare su questa interfaccia, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> che passerà al log di debug un elenco di oggetti <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> contenenti informazioni sugli errori.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="4b8fc-108">Dopo avere implementato l'interfaccia, si recuperano le informazioni sull'errore pubblicando un'istanza di quell'implementazione nel contesto di modifica.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="4b8fc-109">Implementare l'interfaccia IValidationErrorService</span><span class="sxs-lookup"><span data-stu-id="4b8fc-109">Implement the IValidationErrorService Interface</span></span>  
  
1.  <span data-ttu-id="4b8fc-110">Di seguito è riportato un esempio di codice per un'implementazione semplice che scriverà gli errori di convalida nel log di debug.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="4b8fc-111">Pubblicazione del contesto di modifica</span><span class="sxs-lookup"><span data-stu-id="4b8fc-111">Publishing to the Editing Context</span></span>  
  
1.  <span data-ttu-id="4b8fc-112">Di seguito è riportato il codice per la pubblicazione nel contesto di modifica.</span><span class="sxs-lookup"><span data-stu-id="4b8fc-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
