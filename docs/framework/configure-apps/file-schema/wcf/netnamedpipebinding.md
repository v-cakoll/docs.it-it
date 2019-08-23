---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: 475c7dfa618cffa70942fc1e02a75910da847701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933097"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="4b2ae-101">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="4b2ae-101">\<netNamedPipeBinding></span></span>
<span data-ttu-id="4b2ae-102">Definisce un'associazione che è protetta, affidabile, ottimizzata per le comunicazioni tra processi nel computer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-102">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="4b2ae-103">Per impostazione predefinita, genera uno stack di comunicazione in fase di esecuzione con WS-ReliableMessaging per affidabilità, sicurezza del trasporto per la sicurezza del trasferimento, named pipe per il recapito dei messaggi e codifica binaria dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-103">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
 <span data-ttu-id="4b2ae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4b2ae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b2ae-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="4b2ae-105">\<bindings></span></span>  
<span data-ttu-id="4b2ae-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="4b2ae-106">\<netNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b2ae-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b2ae-107">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b2ae-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b2ae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4b2ae-109">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b2ae-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b2ae-110">Attributes</span></span>  
  
|<span data-ttu-id="4b2ae-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4b2ae-111">Attribute</span></span>|<span data-ttu-id="4b2ae-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2ae-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b2ae-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="4b2ae-113">closeTimeout</span></span>|<span data-ttu-id="4b2ae-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4b2ae-115">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b2ae-116">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4b2ae-117">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="4b2ae-117">hostNameComparisonMode</span></span>|<span data-ttu-id="4b2ae-118">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="4b2ae-119">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="4b2ae-120">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="4b2ae-121">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="4b2ae-121">maxBufferPoolSize</span></span>|<span data-ttu-id="4b2ae-122">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-122">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="4b2ae-123">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="4b2ae-123">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="4b2ae-124">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-124">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="4b2ae-125">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-125">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="4b2ae-126">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-126">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="4b2ae-127">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-127">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="4b2ae-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="4b2ae-128">maxBufferSize</span></span>|<span data-ttu-id="4b2ae-129">Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="4b2ae-130">Se il buffer è pieno, i dati in eccesso rimangono nel socket sottostante fino a che non è di nuovo disponibile spazio nel buffer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-130">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="4b2ae-131">Questo valore non può essere inferiore a `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-131">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="4b2ae-132">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-132">The default is 65536.</span></span> <span data-ttu-id="4b2ae-133">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="4b2ae-134">maxConnections</span><span class="sxs-lookup"><span data-stu-id="4b2ae-134">maxConnections</span></span>|<span data-ttu-id="4b2ae-135">Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-135">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="4b2ae-136">Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-136">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="4b2ae-137">Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-137">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="4b2ae-138">Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-138">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="4b2ae-139">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-139">The default is 10.</span></span>|  
|<span data-ttu-id="4b2ae-140">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="4b2ae-140">maxReceivedMessageSize</span></span>|<span data-ttu-id="4b2ae-141">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-141">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="4b2ae-142">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-142">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="4b2ae-143">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="4b2ae-144">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-144">The default is 65536.</span></span>|  
|<span data-ttu-id="4b2ae-145">name</span><span class="sxs-lookup"><span data-stu-id="4b2ae-145">name</span></span>|<span data-ttu-id="4b2ae-146">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="4b2ae-147">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4b2ae-148">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-148">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4b2ae-149">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b2ae-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="4b2ae-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="4b2ae-150">openTimeout</span></span>|<span data-ttu-id="4b2ae-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4b2ae-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b2ae-153">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4b2ae-154">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="4b2ae-154">receiveTimeout</span></span>|<span data-ttu-id="4b2ae-155">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4b2ae-156">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b2ae-157">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-157">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="4b2ae-158">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="4b2ae-158">sendTimeout</span></span>|<span data-ttu-id="4b2ae-159">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4b2ae-160">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4b2ae-161">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4b2ae-162">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="4b2ae-162">transactionFlow</span></span>|<span data-ttu-id="4b2ae-163">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-163">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="4b2ae-164">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-164">The default is `false`.</span></span>|  
|<span data-ttu-id="4b2ae-165">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="4b2ae-165">transactionProtocol</span></span>|<span data-ttu-id="4b2ae-166">Specifica il protocollo di transazione da usare con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-166">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="4b2ae-167">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4b2ae-167">Valid values are</span></span><br /><br /> <span data-ttu-id="4b2ae-168">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="4b2ae-168">-   OleTransactions</span></span><br /><span data-ttu-id="4b2ae-169">-   WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="4b2ae-169">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="4b2ae-170">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-170">The default is OleTransactions.</span></span> <span data-ttu-id="4b2ae-171">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-171">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="4b2ae-172">transferMode</span><span class="sxs-lookup"><span data-stu-id="4b2ae-172">transferMode</span></span>|<span data-ttu-id="4b2ae-173">Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-173">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b2ae-174">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b2ae-174">Child Elements</span></span>  
  
|<span data-ttu-id="4b2ae-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b2ae-175">Element</span></span>|<span data-ttu-id="4b2ae-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2ae-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b2ae-177">\<security></span><span class="sxs-lookup"><span data-stu-id="4b2ae-177">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="4b2ae-178">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-178">Defines the security settings for the binding.</span></span> <span data-ttu-id="4b2ae-179">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-179">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|<span data-ttu-id="4b2ae-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4b2ae-180">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="4b2ae-181">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-181">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4b2ae-182">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-182">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b2ae-183">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b2ae-183">Parent Elements</span></span>  
  
|<span data-ttu-id="4b2ae-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b2ae-184">Element</span></span>|<span data-ttu-id="4b2ae-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2ae-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b2ae-186">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4b2ae-186">\<bindings></span></span>](bindings.md)|<span data-ttu-id="4b2ae-187">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-187">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b2ae-188">Note</span><span class="sxs-lookup"><span data-stu-id="4b2ae-188">Remarks</span></span>  
 <span data-ttu-id="4b2ae-189">L'associazione `NetNamedPipeBinding` genera per impostazione predefinita uno stack di comunicazione di runtime che usa la sicurezza del trasporto, le named pipe per il recapito dei messaggi e una codifica dei messaggi binaria.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-189">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="4b2ae-190">Questa associazione rappresenta una scelta fornita dal sistema Windows Communication Foundation (WCF) appropriata per la comunicazione su computer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-190">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="4b2ae-191">Supporta inoltre le transazioni.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-191">It also supports transactions.</span></span>  
  
 <span data-ttu-id="4b2ae-192">La configurazione predefinita per `NetNamedPipeBinding` è simile alla configurazione fornita da `NetTcpBinding`, ma è più semplice poiché l'implementazione WCF è destinata solo all'utilizzo su computer e le funzionalità esposte sono di conseguenza minori.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-192">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="4b2ae-193">La differenza più evidente è che per l'impostazione di `securityMode` sono disponibili solo le opzioni `None` e `Transport`.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-193">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="4b2ae-194">Il supporto della sicurezza SOAP non è incluso fra le opzioni.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-194">SOAP security support is not an included option.</span></span> <span data-ttu-id="4b2ae-195">Il comportamento di sicurezza può essere configurato usando l'attributo `securityMode` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-195">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b2ae-196">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b2ae-196">Example</span></span>  
 <span data-ttu-id="4b2ae-197">Nell'esempio seguente è dimostrata l'associazione netNamedPipeBinding, che fornisce comunicazione tra processi sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-197">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="4b2ae-198">Le named pipe non funzionano tra computer.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-198">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="4b2ae-199">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="4b2ae-200">Il tipo di associazione è specificato nell'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-200">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="4b2ae-201">Se si desidera configurare l'associazione netNamedPipeBinding e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-201">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="4b2ae-202">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-202">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="4b2ae-203">In questo esempio, la configurazione di associazione è denominata Binding1.</span><span class="sxs-lookup"><span data-stu-id="4b2ae-203">In this example, the binding configuration is named Binding1.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="4b2ae-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b2ae-204">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [<span data-ttu-id="4b2ae-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b2ae-205">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="4b2ae-206">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4b2ae-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4b2ae-207">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="4b2ae-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4b2ae-208">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="4b2ae-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
