---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139335"
---
# \<netTcpBinding>

<span data-ttu-id="9a111-101">Specifica un'associazione protetta, affidabile e ottimizzata adatta per le comunicazioni fra computer.</span><span class="sxs-lookup"><span data-stu-id="9a111-101">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="9a111-102">Per impostazione predefinita, genera uno stack di comunicazione in fase di runtime con Windows per la sicurezza per garantire la sicurezza e l'autenticazione dei messaggi, TCP per il recapito dei messaggi e la codifica binaria dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9a111-102">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="9a111-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a111-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a111-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9a111-104">Attributes and elements</span></span>

<span data-ttu-id="9a111-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9a111-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a111-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="9a111-106">Attributes</span></span>  
  
|<span data-ttu-id="9a111-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="9a111-107">Attribute</span></span>|<span data-ttu-id="9a111-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a111-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9a111-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="9a111-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9a111-110">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a111-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a111-111">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a111-111">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="9a111-112">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="9a111-112">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="9a111-113">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="9a111-113">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="9a111-114">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="9a111-114">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="9a111-115">Numero intero positivo che specifica il numero massimo di canali di attesa accettati nel listener.</span><span class="sxs-lookup"><span data-stu-id="9a111-115">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="9a111-116">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="9a111-116">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="9a111-117">L'attributo `connectionTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9a111-117">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="9a111-118">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="9a111-118">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="9a111-119">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-119">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9a111-120">Il valore predefinito è 512 \* 1024 byte.</span><span class="sxs-lookup"><span data-stu-id="9a111-120">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="9a111-121">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="9a111-121">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="9a111-122">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="9a111-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="9a111-123">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="9a111-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="9a111-124">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="9a111-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="9a111-125">Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria.</span><span class="sxs-lookup"><span data-stu-id="9a111-125">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="9a111-126">Se l'attributo `transferMode` è uguale a `Buffered`, questo attributo deve essere uguale al valore dell'attributo `maxReceivedMessageSize`.</span><span class="sxs-lookup"><span data-stu-id="9a111-126">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="9a111-127">Se l'attributo `transferMode` è uguale a `Streamed`, questo attributo non può essere superiore al valore dell'attributo `maxReceivedMessageSize` e deve essere uguale almeno alla dimensione delle intestazioni.</span><span class="sxs-lookup"><span data-stu-id="9a111-127">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="9a111-128">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="9a111-128">The default is 65536.</span></span> <span data-ttu-id="9a111-129">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a111-129">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="9a111-130">Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà.</span><span class="sxs-lookup"><span data-stu-id="9a111-130">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="9a111-131">Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="9a111-131">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="9a111-132">Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="9a111-132">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="9a111-133">Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.</span><span class="sxs-lookup"><span data-stu-id="9a111-133">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="9a111-134">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="9a111-134">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="9a111-135">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="9a111-136">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="9a111-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="9a111-137">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="9a111-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9a111-138">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="9a111-138">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="9a111-139">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9a111-140">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9a111-141">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="9a111-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9a111-142">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a111-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9a111-143">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="9a111-143">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9a111-144">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a111-144">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a111-145">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a111-145">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="9a111-146">Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione.</span><span class="sxs-lookup"><span data-stu-id="9a111-146">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="9a111-147">Se è `false`, ciascuna associazione usa la propria porta esclusiva.</span><span class="sxs-lookup"><span data-stu-id="9a111-147">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="9a111-148">Questa impostazione è appropriata solo per i servizi in quanto non ha effetto per i client.</span><span class="sxs-lookup"><span data-stu-id="9a111-148">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9a111-149">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="9a111-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9a111-150">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a111-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a111-151">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="9a111-151">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9a111-152">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="9a111-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9a111-153">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a111-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a111-154">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a111-154">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="9a111-155">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="9a111-155">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="9a111-156">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="9a111-156">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="9a111-157">Specifica il protocollo di transazione da usare con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-157">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="9a111-158">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="9a111-158">Valid values are</span></span><br /><br /> <span data-ttu-id="9a111-159">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="9a111-159">-   OleTransactions</span></span><br /><span data-ttu-id="9a111-160">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="9a111-160">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="9a111-161">L'impostazione predefinita è OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="9a111-161">The default is OleTransactions.</span></span> <span data-ttu-id="9a111-162">L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="9a111-162">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="9a111-163">Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="9a111-163">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a111-164">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a111-164">Child elements</span></span>  
  
|<span data-ttu-id="9a111-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a111-165">Element</span></span>|<span data-ttu-id="9a111-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a111-166">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="9a111-167">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-167">Defines the security settings for the binding.</span></span> <span data-ttu-id="9a111-168">L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9a111-168">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="9a111-169">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-169">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9a111-170">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="9a111-170">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="9a111-171">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="9a111-171">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a111-172">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9a111-172">Parent elements</span></span>  
  
|<span data-ttu-id="9a111-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a111-173">Element</span></span>|<span data-ttu-id="9a111-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a111-174">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="9a111-175">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9a111-175">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a111-176">Commenti</span><span class="sxs-lookup"><span data-stu-id="9a111-176">Remarks</span></span>

<span data-ttu-id="9a111-177">Per impostazione predefinita, questa associazione genera uno stack di comunicazione runtime che, oltre a implementare la codifica binaria dei messaggi, usa la sicurezza del trasporto e il protocollo TCP per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9a111-177">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="9a111-178">Questa associazione è una scelta fornita dal sistema Windows Communication Foundation (WCF) appropriata per la comunicazione su una rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="9a111-178">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="9a111-179">La configurazione predefinita per `netTcpBinding` è più veloce rispetto alla configurazione fornita da `wsHttpBinding` , ma è destinata solo alla comunicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="9a111-179">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="9a111-180">Il comportamento di sicurezza può essere configurato usando l'attributo `securityMode` facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9a111-180">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="9a111-181">L'utilizzo del protocollo WS-ReliableMessaging può essere configurato usando l'attributo facoltativo `reliableSessionEnabled`.</span><span class="sxs-lookup"><span data-stu-id="9a111-181">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="9a111-182">La messaggistica affidabile è tuttavia disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a111-182">But reliable messaging is off by default.</span></span> <span data-ttu-id="9a111-183">Più in generale, le associazioni HTTP fornite dal sistema, ad esempio `wsHttpBinding` e `basicHttpBinding`, sono configurate in modo da attivare modalità di supporto per impostazione predefinita, mentre l'associazione `netTcpBinding` le disattiva per impostazione predefinita e pertanto è necessario fornire un consenso esplicito per ottenere il supporto, ad esempio, per una delle specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="9a111-183">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="9a111-184">Ciò significa che la configurazione predefinita per le associazioni TCP è più veloce nello scambio dei messaggi tra endpoint rispetto a quelle predefinite per le associazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a111-184">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a111-185">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a111-185">Example</span></span>

<span data-ttu-id="9a111-186">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="9a111-186">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="9a111-187">Il tipo di associazione è specificato nell'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="9a111-187">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="9a111-188">Se si desidera configurare l'associazione netTcpBinding e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-188">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="9a111-189">L'endpoint deve fare riferimento alla configurazione di associazione con un attributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="9a111-189">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="9a111-190">Nell'esempio seguente viene modificata una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="9a111-190">In the following example, a binding configuration is defined.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a111-191">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9a111-191">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="9a111-192">Binding</span><span class="sxs-lookup"><span data-stu-id="9a111-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a111-193">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9a111-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9a111-194">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="9a111-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
