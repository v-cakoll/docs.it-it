---
title: 'Procedure consigliate: intermediari'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: a7c037b5942a404b1ff790638979a8e430394151
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320790"
---
# <a name="best-practices-intermediaries"></a>Procedure consigliate: intermediari
Assicurarsi di gestire gli errori correttamente nella chiamata agli intermediari verificando che i canali lato servizio degli intermediari vengano chiusi in modo appropriato.  
  
 Si consideri lo scenario seguente. Un client esegue una chiamata a un intermediario che quindi chiama un servizio back-end.  Il servizio back-end non definisce contratti di errori, pertanto qualsiasi errore generato da questo servizio verrà considerato come errore non tipizzato.  Il servizio back-end genera un'<xref:System.ApplicationException> e WCF interrompe correttamente il canale sul lato servizio. L'oggetto <xref:System.ApplicationException> viene quindi rilevato come oggetto <xref:System.ServiceModel.FaultException> generato per l'intermediario. L'intermediario genera nuovamente l'oggetto <xref:System.ApplicationException>. In WCF l'eccezione viene interpretata come errore non tipizzato proveniente dall'intermediario e inoltrata al client. Alla ricezione dell'errore, sia l'intermediario che il client lo imputano ai rispettivi canali lato client. Il canale lato servizio dell'intermediario rimane tuttavia aperto perché non viene rilevato che l'errore è irreversibile.  
  
 La procedura consigliata in questo scenario è rilevare se l'errore proveniente dal servizio è irreversibile. In caso affermativo, l'intermediario dovrebbe bloccare il proprio canale lato servizio come illustrato nel seguente frammento di codice.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Gestione errori WCF](wcf-error-handling.md)
- [Specifica e gestione degli errori in contratti e servizi](specifying-and-handling-faults-in-contracts-and-services.md)
