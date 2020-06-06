---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 01360ae8288b3cb7374597ad77935f634eb0a519
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139278"
---
# \<wsDualHttpBinding>
<span data-ttu-id="250d8-101">Definisce un'associazione protetta, affidabile e interoperabile adatta per contratti di servizio duplex o per la comunicazione tramite intermediari SOAP.</span><span class="sxs-lookup"><span data-stu-id="250d8-101">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="250d8-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="250d8-102">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="250d8-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="250d8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="250d8-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="250d8-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="250d8-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="250d8-105">Attributes</span></span>  
  
|<span data-ttu-id="250d8-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="250d8-106">Attribute</span></span>|<span data-ttu-id="250d8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250d8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="250d8-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="250d8-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="250d8-109">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="250d8-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="250d8-110">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="250d8-110">The default is `false`.</span></span>|  
|<span data-ttu-id="250d8-111">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="250d8-111">clientBaseAddress</span></span>|<span data-ttu-id="250d8-112">URI che imposta l'indirizzo di base che il client ascolta per i messaggi di risposta dal servizio.</span><span class="sxs-lookup"><span data-stu-id="250d8-112">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="250d8-113">Se viene specificato, questo indirizzo (più un GUID per ogni canale) viene usato per l'ascolto.</span><span class="sxs-lookup"><span data-stu-id="250d8-113">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="250d8-114">Se il valore non viene specificato, l'indirizzo di base del client viene generato in un modo specifico del trasporto.</span><span class="sxs-lookup"><span data-stu-id="250d8-114">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="250d8-115">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="250d8-115">The default is `null`.</span></span>|  
|<span data-ttu-id="250d8-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="250d8-116">closeTimeout</span></span>|<span data-ttu-id="250d8-117">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="250d8-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="250d8-118">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="250d8-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="250d8-119">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="250d8-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="250d8-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="250d8-120">hostnameComparisonMode</span></span>|<span data-ttu-id="250d8-121">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="250d8-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="250d8-122">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="250d8-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="250d8-123">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="250d8-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="250d8-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="250d8-124">maxBufferPoolSize</span></span>|<span data-ttu-id="250d8-125">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="250d8-126">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="250d8-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="250d8-127">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="250d8-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="250d8-128">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="250d8-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="250d8-129">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="250d8-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="250d8-130">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="250d8-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="250d8-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="250d8-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="250d8-132">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="250d8-133">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="250d8-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="250d8-134">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="250d8-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="250d8-135">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="250d8-135">The default is 65536.</span></span>|  
|<span data-ttu-id="250d8-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="250d8-136">messageEncoding</span></span>|<span data-ttu-id="250d8-137">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="250d8-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="250d8-138">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="250d8-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="250d8-139">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="250d8-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="250d8-140">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="250d8-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="250d8-141">-Il valore predefinito è testo.</span><span class="sxs-lookup"><span data-stu-id="250d8-141">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="250d8-142">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="250d8-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="250d8-143">name</span><span class="sxs-lookup"><span data-stu-id="250d8-143">name</span></span>|<span data-ttu-id="250d8-144">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="250d8-145">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="250d8-146">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="250d8-146">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="250d8-147">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="250d8-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="250d8-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="250d8-148">openTimeout</span></span>|<span data-ttu-id="250d8-149">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="250d8-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="250d8-150">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="250d8-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="250d8-151">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="250d8-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="250d8-152">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="250d8-152">proxyAddress</span></span>|<span data-ttu-id="250d8-153">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="250d8-153">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="250d8-154">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="250d8-154">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="250d8-155">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="250d8-155">The default is `null`.</span></span>|  
|<span data-ttu-id="250d8-156">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="250d8-156">receiveTimeout</span></span>|<span data-ttu-id="250d8-157">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="250d8-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="250d8-158">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="250d8-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="250d8-159">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="250d8-159">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="250d8-160">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="250d8-160">sendTimeout</span></span>|<span data-ttu-id="250d8-161">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="250d8-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="250d8-162">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="250d8-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="250d8-163">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="250d8-163">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="250d8-164">textEncoding</span><span class="sxs-lookup"><span data-stu-id="250d8-164">textEncoding</span></span>|<span data-ttu-id="250d8-165">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="250d8-166">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="250d8-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="250d8-167">-BigEndianUnicode: codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="250d8-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="250d8-168">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="250d8-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="250d8-169">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="250d8-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="250d8-170">Il valore predefinito è UTF8.</span><span class="sxs-lookup"><span data-stu-id="250d8-170">The default is UTF8.</span></span> <span data-ttu-id="250d8-171">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="250d8-171">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="250d8-172">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="250d8-172">transactionFlow</span></span>|<span data-ttu-id="250d8-173">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="250d8-173">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="250d8-174">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="250d8-174">The default is `false`.</span></span>|  
|<span data-ttu-id="250d8-175">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="250d8-175">useDefaultWebProxy</span></span>|<span data-ttu-id="250d8-176">Valore booleano che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="250d8-176">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="250d8-177">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="250d8-177">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="250d8-178">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="250d8-178">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="250d8-179">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="250d8-179">Child Elements</span></span>  
  
|<span data-ttu-id="250d8-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="250d8-180">Element</span></span>|<span data-ttu-id="250d8-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250d8-181">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="250d8-182">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-182">Defines the security settings for the binding.</span></span> <span data-ttu-id="250d8-183">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="250d8-183">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="250d8-184">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="250d8-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="250d8-185">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="250d8-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="250d8-186">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="250d8-186">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="250d8-187">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="250d8-187">Parent Elements</span></span>  
  
|<span data-ttu-id="250d8-188">Elemento</span><span class="sxs-lookup"><span data-stu-id="250d8-188">Element</span></span>|<span data-ttu-id="250d8-189">Descrizione</span><span class="sxs-lookup"><span data-stu-id="250d8-189">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="250d8-190">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="250d8-190">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="250d8-191">Commenti</span><span class="sxs-lookup"><span data-stu-id="250d8-191">Remarks</span></span>  
 <span data-ttu-id="250d8-192">`WSDualHttpBinding` fornisce lo stesso supporto per i protocolli di servizi Web di `WSHttpBinding`, ma esclusivamente per l'uso con contratti duplex.</span><span class="sxs-lookup"><span data-stu-id="250d8-192">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="250d8-193">`WSDualHttpBinding` supporta solo la sicurezza SOAP e richiede un sistema di messaggistica affidabile.</span><span class="sxs-lookup"><span data-stu-id="250d8-193">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="250d8-194">Per questa associazione è necessario che il client disponga di un URI pubblico che fornisca un endpoint di callback per il servizio.</span><span class="sxs-lookup"><span data-stu-id="250d8-194">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="250d8-195">A tale scopo, usare l'attributo `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="250d8-195">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="250d8-196">Un'associazione duale espone l'indirizzo IP del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="250d8-196">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="250d8-197">Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.</span><span class="sxs-lookup"><span data-stu-id="250d8-197">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="250d8-198">Questa associazione può essere usata per comunicare in modo affidabile attraverso uno o più intermediari SOAP.</span><span class="sxs-lookup"><span data-stu-id="250d8-198">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="250d8-199">Per impostazione predefinita, questa associazione genera uno stack di runtime con WS-ReliableMessaging per l'affidabilità, WS-Security per la sicurezza del messaggio e l'autenticazione, HTTP per il recapito dei messaggi e una codifica messaggi Text/XML.</span><span class="sxs-lookup"><span data-stu-id="250d8-199">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="250d8-200">Esempio</span><span class="sxs-lookup"><span data-stu-id="250d8-200">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="250d8-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250d8-201">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="250d8-202">Binding</span><span class="sxs-lookup"><span data-stu-id="250d8-202">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="250d8-203">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="250d8-203">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="250d8-204">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="250d8-204">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
