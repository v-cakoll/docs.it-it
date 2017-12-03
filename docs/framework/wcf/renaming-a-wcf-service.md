---
title: Ridenominazione di un servizio WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c2ecd78a7d72b86460f4d1972c42c8550010f02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="eda24-102">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eda24-102">Renaming a WCF Service</span></span>
<span data-ttu-id="eda24-103">In questo argomento viene illustrato come ridenominare un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda24-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="eda24-104">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eda24-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="eda24-105">Per ridenominare un servizio di un modello di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="eda24-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="eda24-106">Modificare il nome della classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="eda24-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="eda24-107">Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eda24-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="eda24-108">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="eda24-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="eda24-109">Se il servizio è WebHosted, utilizza un file *.svc.</span><span class="sxs-lookup"><span data-stu-id="eda24-109">If your service is webhosted, it uses an *.svc file.</span></span> <span data-ttu-id="eda24-110">Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eda24-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="eda24-111">Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="eda24-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="eda24-112">Ridenominazione del contratto di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="eda24-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="eda24-113">Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="eda24-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="eda24-114">Modificare il nome del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="eda24-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="eda24-115">Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eda24-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="eda24-116">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="eda24-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
