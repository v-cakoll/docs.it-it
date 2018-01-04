---
title: "Agilità di crittografia nella sicurezza WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7d99ada67255d0ced8bbabc2ab6fc645e6ba9e35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="cebab-102">Agilità di crittografia nella sicurezza WCF</span><span class="sxs-lookup"><span data-stu-id="cebab-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="cebab-103">In questo esempio viene illustrato come specificare un algoritmo standard/personalizzato per offrire un'implementazione di crittografia Agile in un servizio e in un client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cebab-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span> <span data-ttu-id="cebab-104">L'esempio è costituito dai progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cebab-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="cebab-105">Service</span><span class="sxs-lookup"><span data-stu-id="cebab-105">Service</span></span>  
 <span data-ttu-id="cebab-106">Si tratta di un self-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio che implementa il `ICalculator` l'interfaccia e protegge l'endpoint usando il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con sessione protetta e sessione affidabile disabilitate.</span><span class="sxs-lookup"><span data-stu-id="cebab-106">This is a self-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="cebab-107">Il servizio definisce una classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="cebab-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="cebab-108">Client</span><span class="sxs-lookup"><span data-stu-id="cebab-108">Client</span></span>  
 <span data-ttu-id="cebab-109">Si tratta di un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che accede al servizio dopo l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="cebab-109">This is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]client that accesses the service after successful authentication.</span></span> <span data-ttu-id="cebab-110">Richiama le operazioni esposte dall'interfaccia `ICalculator` e viene implementa dal servizio.</span><span class="sxs-lookup"><span data-stu-id="cebab-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="cebab-111">Il servizio definisce inoltre la stessa classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="cebab-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="cebab-112">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="cebab-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="cebab-113">Aprire la soluzione CryptoAgility.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cebab-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="cebab-114">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="cebab-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="cebab-115">Aprire [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] e passare alla directory \WCF\Basic\Security\CryptoAgility\Service\bin ed eseguire il file service.exe con privilegi di amministratore facendo service.exe **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cebab-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="cebab-116">Passare alla directory \WCF\Basic\Security\CryptoAgility\Client\bin ed eseguire il file client.exe.</span><span class="sxs-lookup"><span data-stu-id="cebab-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cebab-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="cebab-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cebab-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="cebab-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cebab-119">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cebab-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cebab-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="cebab-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="cebab-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cebab-121">See Also</span></span>  
 [<span data-ttu-id="cebab-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cebab-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
