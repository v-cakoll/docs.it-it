---
title: 'Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata'
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: a3d993f55bf130039905f1a6512a7ae104512432
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310200"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata
In questo argomento viene descritto come recuperare e pubblicare errori di convalida in un [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] riallocato. Viene in tal modo fornita la procedura per confermare che un flusso di lavoro in una finestra di progettazione riallocata è valido.  
  
 Questa attività dispone di due parti. La prima consiste nel fornire un'implementazione di <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  È disponibile metodo critico da implementare su questa interfaccia, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> che passerà al log di debug un elenco di oggetti <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> contenenti informazioni sugli errori.  Dopo avere implementato l'interfaccia, si recuperano le informazioni sull'errore pubblicando un'istanza di quell'implementazione nel contesto di modifica.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementare l'interfaccia IValidationErrorService  
  
1. Di seguito è riportato un esempio di codice per un'implementazione semplice che scriverà gli errori di convalida nel log di debug.  
  
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
  
### <a name="publishing-to-the-editing-context"></a>Pubblicazione del contesto di modifica  
  
1. Di seguito è riportato il codice per la pubblicazione nel contesto di modifica.  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
