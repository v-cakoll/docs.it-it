---
title: Agilità di crittografia nella sicurezza WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 64519e51b82780ce2b355251245d77bff0a9e73b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002209"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="bfcf6-102">Agilità di crittografia nella sicurezza WCF</span><span class="sxs-lookup"><span data-stu-id="bfcf6-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="bfcf6-103">In questo esempio viene illustrato come specificare un algoritmo standard/personalizzato per fornire un'implementazione di crittografia agile in un servizio e client Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bfcf6-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="bfcf6-104">L'esempio è costituito dai progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfcf6-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="bfcf6-105">**Service**</span><span class="sxs-lookup"><span data-stu-id="bfcf6-105">**Service**</span></span>

<span data-ttu-id="bfcf6-106">Si tratta di un servizio WCF self-hosted che implementa il `ICalculator` l'interfaccia e protegge l'endpoint usando il <xref:System.ServiceModel.WSHttpBinding> con sessione protetta e sessione affidabile disabilitate.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="bfcf6-107">Il servizio definisce una classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="bfcf6-108">**Client**</span><span class="sxs-lookup"><span data-stu-id="bfcf6-108">**Client**</span></span>

<span data-ttu-id="bfcf6-109">Si tratta di un client WCF che accede al servizio al termine dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="bfcf6-110">Richiama le operazioni esposte dall'interfaccia `ICalculator` e viene implementa dal servizio.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="bfcf6-111">Il servizio definisce inoltre la stessa classe `SecurityAlgorithmSuite` personalizzata per specificare gli algoritmi di crittografia da usare per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="bfcf6-112">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="bfcf6-112">To use this sample</span></span>

1. <span data-ttu-id="bfcf6-113">Aprire la soluzione Cryptoagility in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="bfcf6-114">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="bfcf6-115">Aprire [!INCLUDE[fileExplorer](~/includes/fileexplorer-md.md)] e passare alla directory \WCF\Basic\Security\CryptoAgility\Service\bin ed eseguire il file service.exe con privilegi di amministratore facendo clic service.exe e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-115">Open [!INCLUDE[fileExplorer](~/includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="bfcf6-116">Passare alla directory \WCF\Basic\Security\CryptoAgility\Client\bin ed eseguire il file client.exe.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfcf6-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bfcf6-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="bfcf6-119">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfcf6-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bfcf6-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="bfcf6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfcf6-121">See also</span></span>

- [<span data-ttu-id="bfcf6-122">Windows Communication Foundation Security</span><span class="sxs-lookup"><span data-stu-id="bfcf6-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)