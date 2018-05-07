---
title: 'Procedure consigliate: intermediari'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: d69baae9b4f5851f60d8d1336c40e0d18db8e77d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-intermediaries"></a>Procedure consigliate: intermediari
Assicurarsi di gestire gli errori correttamente nella chiamata agli intermediari verificando che i canali lato servizio degli intermediari vengano chiusi in modo appropriato.  
  
 Si consideri lo scenario seguente. Un client esegue una chiamata a un intermediario che quindi chiama un servizio back-end.  Il servizio back-end non definisce contratti di errori, pertanto qualsiasi errore generato da questo servizio verrà considerato come errore non tipizzato.  Il servizio back-end di genera un <xref:System.ApplicationException> e WCF viene correttamente interrotto il canale lato servizio. L'oggetto <xref:System.ApplicationException> viene quindi rilevato come oggetto <xref:System.ServiceModel.FaultException> generato per l'intermediario. L'intermediario genera nuovamente l'oggetto <xref:System.ApplicationException>. In WCF l'eccezione viene interpretata come errore non tipizzato proveniente dall'intermediario e inoltrata al client. Alla ricezione dell'errore, sia l'intermediario che il client lo imputano ai rispettivi canali lato client. Il canale lato servizio dell'intermediario rimane tuttavia aperto perché non viene rilevato che l'errore è irreversibile.  
  
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
    Else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione errori WCF](../../../docs/framework/wcf/wcf-error-handling.md)  
 [Specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
