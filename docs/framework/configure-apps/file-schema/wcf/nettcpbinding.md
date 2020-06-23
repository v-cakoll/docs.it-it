---
title: <netTcpBinding>
description: Rappresenta un'associazione protetta, affidabile e ottimizzata progettata solo per le comunicazioni tra computer WCF tramite TCP. La messaggistica affidabile è disattivata per impostazione predefinita.
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: 95c2c691bf328050f3d189c790d111d2fdeb1bb0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243997"
---
# \<netTcpBinding>

<span data-ttu-id="0a389-103">Specifica un'associazione protetta, affidabile e ottimizzata adatta per le comunicazioni fra computer.</span><span class="sxs-lookup"><span data-stu-id="0a389-103">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="0a389-104">Per impostazione predefinita, genera uno stack di comunicazione in fase di runtime con Windows per la sicurezza per garantire la sicurezza e l'autenticazione dei messaggi, TCP per il recapito dei messaggi e la codifica binaria dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="0a389-104">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="0a389-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a389-105">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a389-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0a389-106">Attributes and elements</span></span>

<span data-ttu-id="0a389-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0a389-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a389-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="0a389-108">Attributes</span></span>  
  
|<span data-ttu-id="0a389-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="0a389-109">Attribute</span></span>|<span data-ttu-id="0a389-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a389-110">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="0a389-111">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="0a389-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="0a389-112">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0a389-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0a389-113">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0a389-113">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="0a389-114">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="0a389-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="0a389-115">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="0a389-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="0a389-116">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="0a389-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="0a389-117">Numero intero positivo che specifica il numero massimo di canali di attesa accettati nel listener.</span><span class="sxs-lookup"><span data-stu-id="0a389-117">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="0a389-118">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="0a389-118">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="0a389-119">L'attributo `connectionTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0a389-119">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="0a389-120">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="0a389-120">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="0a389-121">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="0a389-122">Il valore predefinito è 512 \* 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="0a389-122">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="0a389-123">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="0a389-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="0a389-124">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="0a389-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="0a389-125">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="0a389-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="0a389-126">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="0a389-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="0a389-127">Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria.</span><span class="sxs-lookup"><span data-stu-id="0a389-127">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="0a389-128">Se l'attributo `transferMode` è uguale a `Buffered`, questo attributo deve essere uguale al valore dell'attributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="0a389-128">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="0a389-129">Se l'attributo `transferMode` è uguale a `Streamed`, questo attributo non può essere superiore al valore dell'attributo `maxReceivedMessageSize` e deve essere uguale almeno alla dimensione delle intestazioni.</span><span class="sxs-lookup"><span data-stu-id="0a389-129">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="0a389-130">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="0a389-130">The default is 65536.</span></span> <span data-ttu-id="0a389-131">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a389-131">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="0a389-132">Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà.</span><span class="sxs-lookup"><span data-stu-id="0a389-132">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="0a389-133">Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="0a389-133">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="0a389-134">Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="0a389-134">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="0a389-135">Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="0a389-135">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="0a389-136">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="0a389-136">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="0a389-137">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="0a389-138">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a389-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="0a389-139">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="0a389-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="0a389-140">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="0a389-140">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="0a389-141">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="0a389-142">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="0a389-143">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="0a389-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0a389-144">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a389-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="0a389-145">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="0a389-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="0a389-146">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0a389-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0a389-147">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0a389-147">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="0a389-148">Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione.</span><span class="sxs-lookup"><span data-stu-id="0a389-148">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="0a389-149">Se è `false`, ciascuna associazione usa la propria porta esclusiva.</span><span class="sxs-lookup"><span data-stu-id="0a389-149">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="0a389-150">Questa impostazione è appropriata solo per i servizi in quanto non ha effetto per i client.</span><span class="sxs-lookup"><span data-stu-id="0a389-150">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0a389-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="0a389-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="0a389-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0a389-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0a389-153">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="0a389-153">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="0a389-154">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="0a389-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0a389-155">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="0a389-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0a389-156">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0a389-156">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="0a389-157">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="0a389-157">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="0a389-158">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="0a389-158">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="0a389-159">Specifica il protocollo di transazione da usare con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-159">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="0a389-160">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="0a389-160">Valid values are</span></span><br /><br /> <span data-ttu-id="0a389-161">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="0a389-161">-   OleTransactions</span></span><br /><span data-ttu-id="0a389-162">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="0a389-162">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="0a389-163">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="0a389-163">The default is OleTransactions.</span></span> <span data-ttu-id="0a389-164">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="0a389-164">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="0a389-165">Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="0a389-165">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a389-166">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0a389-166">Child elements</span></span>  
  
|<span data-ttu-id="0a389-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a389-167">Element</span></span>|<span data-ttu-id="0a389-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a389-168">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="0a389-169">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-169">Defines the security settings for the binding.</span></span> <span data-ttu-id="0a389-170">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0a389-170">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="0a389-171">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-171">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0a389-172">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0a389-172">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="0a389-173">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="0a389-173">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a389-174">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0a389-174">Parent elements</span></span>  
  
|<span data-ttu-id="0a389-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a389-175">Element</span></span>|<span data-ttu-id="0a389-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a389-176">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="0a389-177">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0a389-177">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a389-178">Commenti</span><span class="sxs-lookup"><span data-stu-id="0a389-178">Remarks</span></span>

<span data-ttu-id="0a389-179">Per impostazione predefinita, questa associazione genera uno stack di comunicazione runtime che, oltre a implementare la codifica binaria dei messaggi, usa la sicurezza del trasporto e il protocollo TCP per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="0a389-179">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="0a389-180">Questa associazione è una scelta fornita dal sistema Windows Communication Foundation (WCF) appropriata per la comunicazione su una rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="0a389-180">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="0a389-181">La configurazione predefinita per `netTcpBinding` è più veloce rispetto alla configurazione fornita da `wsHttpBinding` , ma è destinata solo alla comunicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="0a389-181">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="0a389-182">Il comportamento di sicurezza può essere configurato usando l'attributo `securityMode` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0a389-182">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="0a389-183">L'utilizzo del protocollo WS-ReliableMessaging può essere configurato usando l'attributo facoltativo `reliableSessionEnabled`.</span><span class="sxs-lookup"><span data-stu-id="0a389-183">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="0a389-184">La messaggistica affidabile è tuttavia disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0a389-184">But reliable messaging is off by default.</span></span> <span data-ttu-id="0a389-185">Più in generale, le associazioni HTTP fornite dal sistema, ad esempio `wsHttpBinding` e `basicHttpBinding`, sono configurate in modo da attivare modalità di supporto per impostazione predefinita, mentre l'associazione `netTcpBinding` le disattiva per impostazione predefinita e pertanto è necessario fornire un consenso esplicito per ottenere il supporto, ad esempio, per una delle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="0a389-185">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="0a389-186">Ciò significa che la configurazione predefinita per le associazioni TCP è più veloce nello scambio dei messaggi tra endpoint rispetto a quelle predefinite per le associazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="0a389-186">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a389-187">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a389-187">Example</span></span>

<span data-ttu-id="0a389-188">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="0a389-188">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="0a389-189">Il tipo di associazione è specificato nell'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="0a389-189">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="0a389-190">Se si desidera configurare l'associazione netTcpBinding e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-190">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="0a389-191">L'endpoint deve fare riferimento alla configurazione di associazione con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="0a389-191">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="0a389-192">Nell'esempio seguente viene modificata una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="0a389-192">In the following example, a binding configuration is defined.</span></span>  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="0a389-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a389-193">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="0a389-194">Associazioni</span><span class="sxs-lookup"><span data-stu-id="0a389-194">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0a389-195">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="0a389-195">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0a389-196">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="0a389-196">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
