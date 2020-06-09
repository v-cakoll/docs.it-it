---
title: Codifica MTOM
ms.date: 03/30/2017
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
ms.openlocfilehash: cf048e1e6b2e2785accc1bde0336f07e3d84ae5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602536"
---
# <a name="mtom-encoding"></a><span data-ttu-id="8e149-102">Codifica MTOM</span><span class="sxs-lookup"><span data-stu-id="8e149-102">MTOM Encoding</span></span>
<span data-ttu-id="8e149-103">In questo esempio viene illustrato come utilizzare la codifica dei messaggi MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi) con un WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="8e149-103">This sample demonstrates the use of the Message Transmission Optimization Mechanism (MTOM) message encoding with a WSHttpBinding.</span></span> <span data-ttu-id="8e149-104">MTOM è un meccanismo per trasmettere grandi allegati binari con messaggi SOAP come byte non elaborati, lasciando spazio a messaggi più piccoli.</span><span class="sxs-lookup"><span data-stu-id="8e149-104">MTOM is a mechanism for transmitting large binary attachments with SOAP messages as raw bytes, allowing for smaller messages.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8e149-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8e149-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8e149-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8e149-106">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8e149-107">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="8e149-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8e149-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8e149-108">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 <span data-ttu-id="8e149-109">Per impostazione predefinita, WSHttpBinding invia e riceve messaggi come XML di testo normale.</span><span class="sxs-lookup"><span data-stu-id="8e149-109">By default, the WSHttpBinding sends and received messages as normal text XML.</span></span> <span data-ttu-id="8e149-110">Per abilitare l'invio e la ricezione di messaggi MTOM, impostare l'attributo `messageEncoding` sulla configurazione dell'associazione (come nel codice di esempio seguente) o direttamente sull'associazione utilizzando la proprietà `MessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="8e149-110">To enable sending and receiving MTOM messages, set the `messageEncoding` attribute on the binding's configuration (as in the following example code), or directly on the binding using the `MessageEncoding` property.</span></span> <span data-ttu-id="8e149-111">Il servizio o client ora possono inviare e ricevere messaggi MTOM.</span><span class="sxs-lookup"><span data-stu-id="8e149-111">The service or client can now send and receive MTOM messages.</span></span>  
  
```xml  
<wsHttpBinding>  
  <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom" />  
</wsHttpBinding>  
```  
  
 <span data-ttu-id="8e149-112">Il codificatore MTOM può ottimizzare matrici di byte e flussi.</span><span class="sxs-lookup"><span data-stu-id="8e149-112">The MTOM encoder can optimize arrays of bytes and streams.</span></span> <span data-ttu-id="8e149-113">In questo esempio, l'operazione utilizza un parametro `Stream` e può pertanto essere ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="8e149-113">In this sample, the operation uses a `Stream` parameter and can therefore be optimized.</span></span>  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```
  
 <span data-ttu-id="8e149-114">Il contratto scelto per questo esempio trasmette dati binari al servizio e riceve il numero di byte caricato come valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8e149-114">The contract chosen for this sample transmits binary data to the service and receives the number of bytes uploaded as the return value.</span></span> <span data-ttu-id="8e149-115">Quando il servizio viene installato e il client viene eseguito, esso stampa il numero 1000 che indica che tutti i 1000 byte sono stati ricevuti.</span><span class="sxs-lookup"><span data-stu-id="8e149-115">When the service is installed and the client is run, it prints out the number 1000, which indicates that all 1000 bytes were received.</span></span> <span data-ttu-id="8e149-116">Il resto dell'output elenca le dimensioni del messaggio ottimizzate e non ottimizzate per vari payload.</span><span class="sxs-lookup"><span data-stu-id="8e149-116">The remainder of the output lists optimized and non-optimized message sizes for various payloads.</span></span>  
  
```console
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="8e149-117">Lo scopo di MTOM è ottimizzare la trasmissione di grandi payload binari.</span><span class="sxs-lookup"><span data-stu-id="8e149-117">The purpose for using MTOM is to optimize the transmission of large binary payloads.</span></span> <span data-ttu-id="8e149-118">L'invio di un messaggio SOAP con MTOM crea un sovraccarico evidente per i piccoli payload binari, ma consente grandi risparmi quando essi sono di centinaia di byte.</span><span class="sxs-lookup"><span data-stu-id="8e149-118">Sending a SOAP message using MTOM has a noticeable overhead for small binary payloads, but becomes a great savings when they grow over a few thousand bytes.</span></span> <span data-ttu-id="8e149-119">La ragione di ciò è che XML di testo normale codifica dati binari utilizzando Base 64 che richiede quattro caratteri per ogni tre byte aumentando la dimensione dei dati di un terzo.</span><span class="sxs-lookup"><span data-stu-id="8e149-119">The reason for this is that normal text XML encodes binary data using Base64, which requires four characters for every three bytes, and increases the size of the data by one third.</span></span> <span data-ttu-id="8e149-120">MTOM è in grado di trasmettere dati binari come byte non elaborati, risparmiando i tempi di codifica/decodifica e quindi consentendo di trasmettere messaggi più piccoli.</span><span class="sxs-lookup"><span data-stu-id="8e149-120">MTOM is able to transmit binary data as raw bytes, saving the encoding/decoding time and resulting is smaller messages.</span></span> <span data-ttu-id="8e149-121">La soglia di alcune migliaia di byte è piccola se confrontata alle dimensioni dei documenti commerciali di oggi e a quelle delle fotografie digitali.</span><span class="sxs-lookup"><span data-stu-id="8e149-121">The threshold of a few thousand bytes is small when compared to today's business documents and digital photographs.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8e149-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="8e149-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8e149-123">Installare ASP.NET 4,0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="8e149-123">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="8e149-124">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e149-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="8e149-125">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e149-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="8e149-126">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e149-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
