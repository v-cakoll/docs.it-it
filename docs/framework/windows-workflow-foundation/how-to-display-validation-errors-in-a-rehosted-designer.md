---
title: 'Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: 8f70b190042d167741bbadc4e1645756fe5b830d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512567"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="b9ef0-102">Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata</span><span class="sxs-lookup"><span data-stu-id="b9ef0-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="b9ef0-103">In questo argomento viene descritto come recuperare e pubblicare errori di convalida in un [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] riallocato.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="b9ef0-104">Viene in tal modo fornita la procedura per confermare che un flusso di lavoro in una finestra di progettazione riallocata è valido.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="b9ef0-105">Questa attività dispone di due parti.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-105">This task has two parts.</span></span> <span data-ttu-id="b9ef0-106">La prima consiste nel fornire un'implementazione di <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="b9ef0-107">È disponibile metodo critico da implementare su questa interfaccia, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> che passerà al log di debug un elenco di oggetti <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> contenenti informazioni sugli errori.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="b9ef0-108">Dopo avere implementato l'interfaccia, si recuperano le informazioni sull'errore pubblicando un'istanza di quell'implementazione nel contesto di modifica.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="b9ef0-109">Implementare l'interfaccia IValidationErrorService</span><span class="sxs-lookup"><span data-stu-id="b9ef0-109">Implement the IValidationErrorService Interface</span></span>  
  
1.  <span data-ttu-id="b9ef0-110">Di seguito è riportato un esempio di codice per un'implementazione semplice che scriverà gli errori di convalida nel log di debug.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
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
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="b9ef0-111">Pubblicazione del contesto di modifica</span><span class="sxs-lookup"><span data-stu-id="b9ef0-111">Publishing to the Editing Context</span></span>  
  
1.  <span data-ttu-id="b9ef0-112">Di seguito è riportato il codice per la pubblicazione nel contesto di modifica.</span><span class="sxs-lookup"><span data-stu-id="b9ef0-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
