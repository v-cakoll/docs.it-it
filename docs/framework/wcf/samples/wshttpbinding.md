---
title: WSHttpBinding
ms.date: 03/30/2017
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
ms.openlocfilehash: a78eac52095d3f647efdacc9104a75e46651f389
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596371"
---
# <a name="wshttpbinding"></a><span data-ttu-id="1a7d8-102">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1a7d8-102">WSHttpBinding</span></span>
<span data-ttu-id="1a7d8-103">In questo esempio viene illustrato come implementare un servizio tipico e un client tipico utilizzando Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-103">This sample demonstrates how to implement a typical service and a typical client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1a7d8-104">Questo esempio è costituito da un programma di console client (client.exe) e da una libreria di servizi ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-104">This sample consists of a client console program (client.exe) and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="1a7d8-105">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-105">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="1a7d8-106">Il contratto è definito dall'interfaccia `ICalculator` che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-106">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="1a7d8-107">Il client esegue richieste sincrone a un'operazione matematica specificata e il servizio risponde fornendo il risultato.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-107">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="1a7d8-108">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-108">Client activity is visible in the console window.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a7d8-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1a7d8-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-110">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1a7d8-111">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1a7d8-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-112">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
> <span data-ttu-id="1a7d8-113">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1a7d8-114">Questo esempio espone il `ICalculator` contratto usando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1a7d8-114">This sample exposes the `ICalculator` contract using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="1a7d8-115">La configurazione di questa associazione è stata espansa nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-115">The configuration of this binding has been expanded in the Web.config file.</span></span>  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"
              transactionFlow="false"
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"
              textEncoding="utf-8"
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="1a7d8-116">Sull'elemento `binding` di base, il valore `maxReceivedMessageSize` consente di configurare la dimensione massima di un messaggio in arrivo (in byte).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-116">On the base `binding` element, the `maxReceivedMessageSize` value lets you configure the maximum size of an incoming message (in bytes).</span></span> <span data-ttu-id="1a7d8-117">Il valore `hostNameComparisonMode` consente di configurare se il nome host viene considerato quando si esegue il demultiplexing dei messaggi al servizio.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-117">The `hostNameComparisonMode` value lets you configure whether the hostname is considered when de-multiplexing messages to the service.</span></span> <span data-ttu-id="1a7d8-118">Il valore `messageEncoding` consente di configurare se utilizzare la codifica di testo o MTOM per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-118">The `messageEncoding` value lets you configure whether to use Text or MTOM encoding for messages.</span></span> <span data-ttu-id="1a7d8-119">Il valore `textEncoding` consente di configurare la codifica dei caratteri per i messaggi.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-119">The `textEncoding` value lets you configure the character encoding for messages.</span></span> <span data-ttu-id="1a7d8-120">Il valore `bypassProxyOnLocal` consente di configurare se utilizzare un proxy HTTP per la comunicazione locale.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-120">The `bypassProxyOnLocal` value lets you configure whether to use an HTTP proxy for local communication.</span></span> <span data-ttu-id="1a7d8-121">Il valore `transactionFlow` configura se la transazione corrente viene propagata (se un'operazione è configurata per il flusso delle transazioni).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-121">The `transactionFlow` value configures whether the current transaction is flowed (if an operation is configured for transaction flow).</span></span>  
  
 <span data-ttu-id="1a7d8-122">Nell' [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) elemento il valore booleano Enabled configura se sono abilitate le sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-122">On the [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) element, the enabled Boolean value configures whether reliable sessions are enabled.</span></span> <span data-ttu-id="1a7d8-123">Il valore `ordered` configura se l'ordinamento dei messaggi viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-123">The `ordered` value configures whether message ordering is preserved.</span></span> <span data-ttu-id="1a7d8-124">Il valore `inactivityTimeout` configura per quanto tempo una sessione può essere inattiva prima che venga generato un errore.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-124">The `inactivityTimeout` value configures how long a session can be idle before being faulted.</span></span>  
  
 <span data-ttu-id="1a7d8-125">In il [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) `mode` valore configura la modalità di sicurezza da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-125">On the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md), the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="1a7d8-126">In questo esempio viene utilizzata la sicurezza dei messaggi, motivo per cui viene [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) specificato all'interno di [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="1a7d8-126">In this sample, messages security is being used, which is why the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) is specified inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="1a7d8-127">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1a7d8-128">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1a7d8-129">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1a7d8-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1a7d8-130">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="1a7d8-130">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="1a7d8-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="1a7d8-132">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="1a7d8-133">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1a7d8-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
