---
title: Ridenominazione di un servizio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 1179e7b235130e1967c79843b7a11f55622a01fb
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052052"
---
# <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF
In questo argomento viene descritto come rinominare un servizio Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF  
 Eseguire i passaggi seguenti per rinominare un servizio in un modello di Windows Communication Foundation (WCF),  
  
- Modificare il nome della classe che implementa il servizio.  
  
- Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Se il servizio è WebHosted, viene usato un file con * \* estensione svc* . Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente. Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Ridenominazione del contratto di un servizio WCF  
  
- Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:  
  
- Modificare il nome del contratto di servizio.  
  
- Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
