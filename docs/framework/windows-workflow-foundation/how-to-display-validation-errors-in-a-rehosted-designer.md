---
title: 'Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: d36883eb77864ccc16cb5882d0de216e1aaaa589
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420605"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata
In questo argomento viene descritto come recuperare e pubblicare errori di convalida in un [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] riallocato. Viene in tal modo fornita la procedura per confermare che un flusso di lavoro in una finestra di progettazione riallocata è valido.  
  
 Questa attività dispone di due parti. La prima consiste nel fornire un'implementazione di <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  È disponibile metodo critico da implementare su questa interfaccia, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> che passerà al log di debug un elenco di oggetti <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> contenenti informazioni sugli errori.  Dopo avere implementato l'interfaccia, si recuperano le informazioni sull'errore pubblicando un'istanza di quell'implementazione nel contesto di modifica.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementare l'interfaccia IValidationErrorService  
  
1. Di seguito è riportato un esempio di codice per un'implementazione semplice che scriverà gli errori di convalida nel log di debug.  
  
    ```csharp  
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
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Pubblicazione del contesto di modifica  
  
1. Di seguito è riportato il codice per la pubblicazione nel contesto di modifica.  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
