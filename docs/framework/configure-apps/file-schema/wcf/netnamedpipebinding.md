---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: f1aa68bcdda43fd77bee397c079695f7937faa52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139476"
---
# \<netNamedPipeBinding>
<span data-ttu-id="26185-101">Definisce un'associazione che è protetta, affidabile, ottimizzata per le comunicazioni tra processi nel computer.</span><span class="sxs-lookup"><span data-stu-id="26185-101">Defines a binding that is secure, reliable, optimized for on-machine cross process communication.</span></span> <span data-ttu-id="26185-102">Per impostazione predefinita, genera uno stack di comunicazione in fase di esecuzione con WS-ReliableMessaging per affidabilità, sicurezza del trasporto per la sicurezza del trasferimento, named pipe per il recapito dei messaggi e codifica binaria dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="26185-102">By default, it generates a runtime communication stack with WS-ReliableMessaging for reliability, transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="26185-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26185-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26185-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="26185-104">Attributes and Elements</span></span>  
 <span data-ttu-id="26185-105">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="26185-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26185-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="26185-106">Attributes</span></span>  
  
|<span data-ttu-id="26185-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="26185-107">Attribute</span></span>|<span data-ttu-id="26185-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26185-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26185-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="26185-109">closeTimeout</span></span>|<span data-ttu-id="26185-110">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="26185-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="26185-111">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="26185-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="26185-112">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="26185-112">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="26185-113">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="26185-113">hostNameComparisonMode</span></span>|<span data-ttu-id="26185-114">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="26185-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="26185-115">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="26185-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="26185-116">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="26185-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="26185-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="26185-117">maxBufferPoolSize</span></span>|<span data-ttu-id="26185-118">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-118">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="26185-119">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="26185-119">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="26185-120">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="26185-120">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="26185-121">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="26185-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="26185-122">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="26185-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="26185-123">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="26185-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="26185-124">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="26185-124">maxBufferSize</span></span>|<span data-ttu-id="26185-125">Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria.</span><span class="sxs-lookup"><span data-stu-id="26185-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span> <span data-ttu-id="26185-126">Se il buffer è pieno, i dati in eccesso rimangono nel socket sottostante fino a che non è di nuovo disponibile spazio nel buffer.</span><span class="sxs-lookup"><span data-stu-id="26185-126">If the buffer is full, excess data remains in the underlying socket until the buffer has room again.</span></span> <span data-ttu-id="26185-127">Questo valore non può essere inferiore a `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="26185-127">This value cannot be less than `maxReceivedMessageSize` attribute.</span></span> <span data-ttu-id="26185-128">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="26185-128">The default is 65536.</span></span> <span data-ttu-id="26185-129">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="26185-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|<span data-ttu-id="26185-130">maxConnections</span><span class="sxs-lookup"><span data-stu-id="26185-130">maxConnections</span></span>|<span data-ttu-id="26185-131">Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà.</span><span class="sxs-lookup"><span data-stu-id="26185-131">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="26185-132">Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="26185-132">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="26185-133">Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="26185-133">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="26185-134">Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="26185-134">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="26185-135">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="26185-135">The default is 10.</span></span>|  
|<span data-ttu-id="26185-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="26185-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="26185-137">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="26185-138">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="26185-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="26185-139">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="26185-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="26185-140">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="26185-140">The default is 65536.</span></span>|  
|<span data-ttu-id="26185-141">name</span><span class="sxs-lookup"><span data-stu-id="26185-141">name</span></span>|<span data-ttu-id="26185-142">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-142">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="26185-143">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-143">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="26185-144">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="26185-144">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="26185-145">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="26185-145">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="26185-146">openTimeout</span><span class="sxs-lookup"><span data-stu-id="26185-146">openTimeout</span></span>|<span data-ttu-id="26185-147">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="26185-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="26185-148">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="26185-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="26185-149">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="26185-149">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="26185-150">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="26185-150">receiveTimeout</span></span>|<span data-ttu-id="26185-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="26185-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="26185-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="26185-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="26185-153">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="26185-153">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="26185-154">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="26185-154">sendTimeout</span></span>|<span data-ttu-id="26185-155">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="26185-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="26185-156">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="26185-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="26185-157">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="26185-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="26185-158">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="26185-158">transactionFlow</span></span>|<span data-ttu-id="26185-159">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="26185-159">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="26185-160">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="26185-160">The default is `false`.</span></span>|  
|<span data-ttu-id="26185-161">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="26185-161">transactionProtocol</span></span>|<span data-ttu-id="26185-162">Specifica il protocollo di transazione da usare con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-162">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="26185-163">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="26185-163">Valid values are</span></span><br /><br /> <span data-ttu-id="26185-164">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="26185-164">-   OleTransactions</span></span><br /><span data-ttu-id="26185-165">-WS-AtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="26185-165">-   WS-AtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="26185-166">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="26185-166">The default is OleTransactions.</span></span> <span data-ttu-id="26185-167">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="26185-167">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|<span data-ttu-id="26185-168">transferMode</span><span class="sxs-lookup"><span data-stu-id="26185-168">transferMode</span></span>|<span data-ttu-id="26185-169">Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="26185-169">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26185-170">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="26185-170">Child Elements</span></span>  
  
|<span data-ttu-id="26185-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="26185-171">Element</span></span>|<span data-ttu-id="26185-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26185-172">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="26185-173">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-173">Defines the security settings for the binding.</span></span> <span data-ttu-id="26185-174">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="26185-174">This element is of type <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="26185-175">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-175">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="26185-176">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="26185-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26185-177">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="26185-177">Parent Elements</span></span>  
  
|<span data-ttu-id="26185-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="26185-178">Element</span></span>|<span data-ttu-id="26185-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26185-179">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="26185-180">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="26185-180">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26185-181">Commenti</span><span class="sxs-lookup"><span data-stu-id="26185-181">Remarks</span></span>  
 <span data-ttu-id="26185-182">L'associazione `NetNamedPipeBinding` genera per impostazione predefinita uno stack di comunicazione di runtime che usa la sicurezza del trasporto, le named pipe per il recapito dei messaggi e una codifica dei messaggi binaria.</span><span class="sxs-lookup"><span data-stu-id="26185-182">The `NetNamedPipeBinding` generates a run-time communication stack by default, which uses transport security, named pipes for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="26185-183">Questa associazione rappresenta una scelta fornita dal sistema Windows Communication Foundation (WCF) appropriata per la comunicazione su computer.</span><span class="sxs-lookup"><span data-stu-id="26185-183">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for on-machine communication.</span></span> <span data-ttu-id="26185-184">Supporta inoltre le transazioni.</span><span class="sxs-lookup"><span data-stu-id="26185-184">It also supports transactions.</span></span>  
  
 <span data-ttu-id="26185-185">La configurazione predefinita per `NetNamedPipeBinding` è simile alla configurazione fornita da `NetTcpBinding`, ma è più semplice poiché l'implementazione WCF è destinata solo all'utilizzo su computer e le funzionalità esposte sono di conseguenza minori.</span><span class="sxs-lookup"><span data-stu-id="26185-185">The default configuration for the `NetNamedPipeBinding` is similar to the configuration provided by the `NetTcpBinding`, but it is simpler because the WCF implementation is only meant for on-machine use and consequently there are fewer exposed features.</span></span> <span data-ttu-id="26185-186">La differenza più evidente è che per l'impostazione di `securityMode` sono disponibili solo le opzioni `None` e `Transport`.</span><span class="sxs-lookup"><span data-stu-id="26185-186">The most notable difference is that the `securityMode` setting only offers the `None` and `Transport` options.</span></span> <span data-ttu-id="26185-187">Il supporto della sicurezza SOAP non è incluso fra le opzioni.</span><span class="sxs-lookup"><span data-stu-id="26185-187">SOAP security support is not an included option.</span></span> <span data-ttu-id="26185-188">Il comportamento di sicurezza può essere configurato usando l'attributo `securityMode` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="26185-188">The security behavior is configurable using the optional `securityMode` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26185-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="26185-189">Example</span></span>  
 <span data-ttu-id="26185-190">Nell'esempio seguente è dimostrata l'associazione netNamedPipeBinding, che fornisce comunicazione tra processi sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="26185-190">The following example demonstrates the netNamedPipeBinding binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="26185-191">Le named pipe non funzionano tra computer.</span><span class="sxs-lookup"><span data-stu-id="26185-191">Named pipes do not work across machines.</span></span>  
  
 <span data-ttu-id="26185-192">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="26185-192">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="26185-193">Il tipo di associazione è specificato nell'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="26185-193">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="26185-194">Se si desidera configurare l'associazione netNamedPipeBinding e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="26185-194">If you want to configure the netNamedPipeBinding binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="26185-195">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="26185-195">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="26185-196">In questo esempio, la configurazione di associazione è denominata Binding1.</span><span class="sxs-lookup"><span data-stu-id="26185-196">In this example, the binding configuration is named Binding1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26185-197">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="26185-197">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="26185-198">Binding</span><span class="sxs-lookup"><span data-stu-id="26185-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="26185-199">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="26185-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="26185-200">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="26185-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
