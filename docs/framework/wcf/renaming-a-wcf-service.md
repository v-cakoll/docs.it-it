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
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="3259f-102">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="3259f-102">Renaming a WCF Service</span></span>
<span data-ttu-id="3259f-103">In questo argomento viene descritto come rinominare un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3259f-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="3259f-104">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="3259f-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="3259f-105">Eseguire i passaggi seguenti per rinominare un servizio in un modello di Windows Communication Foundation (WCF),</span><span class="sxs-lookup"><span data-stu-id="3259f-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="3259f-106">Modificare il nome della classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="3259f-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="3259f-107">Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3259f-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="3259f-108">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="3259f-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="3259f-109">Se il servizio è WebHosted, viene usato un file con \* \* estensione svc\* .</span><span class="sxs-lookup"><span data-stu-id="3259f-109">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="3259f-110">Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3259f-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="3259f-111">Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="3259f-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="3259f-112">Ridenominazione del contratto di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="3259f-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="3259f-113">Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3259f-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="3259f-114">Modificare il nome del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="3259f-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="3259f-115">Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3259f-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="3259f-116">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="3259f-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
