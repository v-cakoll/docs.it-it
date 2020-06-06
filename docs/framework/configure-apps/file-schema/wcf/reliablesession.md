---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 95f6646041dc2dd7bae7691a0a9f748c844f50b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738755"
---
# \<reliableSession>
<span data-ttu-id="3998b-101">Definisce l'impostazione per WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="3998b-101">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="3998b-102">Quando questo elemento viene aggiunto a un'associazione personalizzata, il canale risultante può supportare assicurazioni di recapito una volta esatta.</span><span class="sxs-lookup"><span data-stu-id="3998b-102">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a><span data-ttu-id="3998b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3998b-103">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3998b-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3998b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="3998b-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3998b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3998b-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="3998b-106">Attributes</span></span>  
  
|<span data-ttu-id="3998b-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="3998b-107">Attribute</span></span>|<span data-ttu-id="3998b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3998b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3998b-109">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="3998b-109">acknowledgementInterval</span></span>|<span data-ttu-id="3998b-110"><xref:System.TimeSpan> che contiene l'intervallo di attesa massimo del canale per l'invio di un riconoscimento dei messaggi ricevuti fino a quel punto.</span><span class="sxs-lookup"><span data-stu-id="3998b-110">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="3998b-111">Il valore predefinito è 00:00:02.</span><span class="sxs-lookup"><span data-stu-id="3998b-111">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="3998b-112">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="3998b-112">flowControlEnabled</span></span>|<span data-ttu-id="3998b-113">Valore booleano che indica se è attivato il controllo di flusso avanzato, un'implementazione specifica di Microsoft del controllo di flusso per WS-Affidabile Messaging.</span><span class="sxs-lookup"><span data-stu-id="3998b-113">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="3998b-114">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="3998b-114">The default is `true`.</span></span>|  
|<span data-ttu-id="3998b-115">inactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="3998b-115">inactivityTimeout</span></span>|<span data-ttu-id="3998b-116">Valore <xref:System.TimeSpan> che specifica la durata massima durante la quale il canale consente all'altra parte della comunicazione di non inviare messaggi prima di generare un errore per il canale.</span><span class="sxs-lookup"><span data-stu-id="3998b-116">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="3998b-117">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3998b-117">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="3998b-118">L'attività in un canale viene definita come ricezione di messaggi di un'applicazione o di un'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="3998b-118">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="3998b-119">Questa proprietà controlla la durata massima in attività di una sessione inattiva.</span><span class="sxs-lookup"><span data-stu-id="3998b-119">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="3998b-120">Se il periodo di inattività è più lungo, la sessione viene interrotta dall'infrastruttura e viene generato un errore per il canale.</span><span class="sxs-lookup"><span data-stu-id="3998b-120">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="3998b-121">**Nota:**  Non è necessario che l'applicazione invii periodicamente messaggi per mantenerne attiva la connessione.</span><span class="sxs-lookup"><span data-stu-id="3998b-121">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="3998b-122">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="3998b-122">maxPendingChannels</span></span>|<span data-ttu-id="3998b-123">Numero intero che specifica il numero massimo di canali che possono attendere nel listener prima di essere accettati.</span><span class="sxs-lookup"><span data-stu-id="3998b-123">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="3998b-124">Questo valore deve essere compreso tra 1 e 16384 inclusi.</span><span class="sxs-lookup"><span data-stu-id="3998b-124">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="3998b-125">Il valore predefinito è 4.</span><span class="sxs-lookup"><span data-stu-id="3998b-125">The default is 4.</span></span><br /><br /> <span data-ttu-id="3998b-126">I canali sono in sospeso quando attendono di essere accettati.</span><span class="sxs-lookup"><span data-stu-id="3998b-126">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="3998b-127">Una volta che tale limite viene raggiunto, non vengono creati canali.</span><span class="sxs-lookup"><span data-stu-id="3998b-127">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="3998b-128">Invece, questi vengono impostati in modalità sospesa finché questo numero non diminuisce, accettando i canali in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3998b-128">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="3998b-129">Si tratta di un limite per-factory.</span><span class="sxs-lookup"><span data-stu-id="3998b-129">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="3998b-130">Quando la soglia viene raggiunta e un'applicazione remota tenta di stabilire una nuova sessione affidabile, la richiesta è negata e l'operazione di apertura che ha inviato la richiesta produce un errore.</span><span class="sxs-lookup"><span data-stu-id="3998b-130">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="3998b-131">Questo limite non si applica al numero di canali in uscita in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3998b-131">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="3998b-132">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="3998b-132">maxRetryCount</span></span>|<span data-ttu-id="3998b-133">Numero intero che specifica il numero massimo di tentativi di ritrasmissione di un messaggio per il quale un canale affidabile non ha ricevuto un riconoscimento, tramite una chiamata a Send sul canale sottostante.</span><span class="sxs-lookup"><span data-stu-id="3998b-133">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="3998b-134">Questo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="3998b-134">This value should be greater than zero.</span></span> <span data-ttu-id="3998b-135">Il valore predefinito è 8.</span><span class="sxs-lookup"><span data-stu-id="3998b-135">The default is 8.</span></span><br /><br /> <span data-ttu-id="3998b-136">Il valore deve essere un intero maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="3998b-136">This value should be an integer greater than zero.</span></span> <span data-ttu-id="3998b-137">Se non viene ricevuto un riconoscimento dopo l'ultima ritrasmissione, il canale genera un errore.</span><span class="sxs-lookup"><span data-stu-id="3998b-137">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="3998b-138">Un messaggio è considerato trasferito se il recapito al destinatario è stato dato riconosciuto dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="3998b-138">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="3998b-139">Se entro una certa quantità di tempo non è stato ricevuto un riconoscimento per un messaggio trasmesso, l'infrastruttura lo ritrasmette automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3998b-139">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="3998b-140">L'infrastruttura tenta a reinviare il messaggio almeno per il numero di volte specificato da questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="3998b-140">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="3998b-141">Se non viene ricevuto un riconoscimento dopo l'ultima ritrasmissione, il canale genera un errore.</span><span class="sxs-lookup"><span data-stu-id="3998b-141">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="3998b-142">L'infrastruttura usa un algoritmo di interruzione temporanea esponenziale per determinare quando ritrasmettere, in base a un tempo medio di andata e ritorno calcolato.</span><span class="sxs-lookup"><span data-stu-id="3998b-142">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="3998b-143">Il periodo parte inizialmente 1 secondo prima della ritrasmissione raddoppiando il ritardo con ogni tentativo, che si traduce approssimativamente in 8,5 minuti tra il primo tentativo della trasmissione e l'ultimo.</span><span class="sxs-lookup"><span data-stu-id="3998b-143">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="3998b-144">Il momento del primo tentativo di ritrasmissione viene regolato in base al tempo di andata e ritorno calcolato e l'adattamento temporale richiesto da tali tentativi varia di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="3998b-144">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="3998b-145">Questo consente di adattare dinamicamente il tempo di ritrasmissione alle mutevoli condizioni della rete.</span><span class="sxs-lookup"><span data-stu-id="3998b-145">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="3998b-146">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="3998b-146">maxTransferWindowSize</span></span>|<span data-ttu-id="3998b-147">[out] Valore intero che specifica la dimensione massima del buffer.</span><span class="sxs-lookup"><span data-stu-id="3998b-147">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="3998b-148">I valori validi sono compresi tra 1 e 4096 inclusi.</span><span class="sxs-lookup"><span data-stu-id="3998b-148">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="3998b-149">Sul client, questo attributo definisce la dimensione massima del buffer usata da un canale affidabile per contenere i messaggi non riconosciuti dal ricevitore.</span><span class="sxs-lookup"><span data-stu-id="3998b-149">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="3998b-150">L'unità della quota è un messaggio.</span><span class="sxs-lookup"><span data-stu-id="3998b-150">The unit of the quota is a message.</span></span> <span data-ttu-id="3998b-151">Se il buffer è pieno, ulteriori operazioni SNED vengono bloccate.</span><span class="sxs-lookup"><span data-stu-id="3998b-151">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="3998b-152">Sul ricevitore, questo attributo definisce la dimensione massima del buffer usata dal canale per memorizzare i messaggi non ancora inviati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3998b-152">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="3998b-153">Se il buffer è pieno, ulteriori messaggi vengono rilasciati silenziosamente dal ricevitore e richiedono la ritrasmissione da parte del client.</span><span class="sxs-lookup"><span data-stu-id="3998b-153">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="3998b-154">ordered</span><span class="sxs-lookup"><span data-stu-id="3998b-154">ordered</span></span>|<span data-ttu-id="3998b-155">Valore booleano che specifica se viene garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="3998b-155">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="3998b-156">Se l'impostazione è `false`, i messaggi possono arrivare in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="3998b-156">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="3998b-157">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="3998b-157">The default is `true`.</span></span>|  
|<span data-ttu-id="3998b-158">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="3998b-158">reliableMessagingVersion</span></span>|<span data-ttu-id="3998b-159">Un valore valido da <xref:System.ServiceModel.ReliableMessagingVersion> che specifica la versione di WS-ReliableMessaging da usare.</span><span class="sxs-lookup"><span data-stu-id="3998b-159">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3998b-160">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3998b-160">Child Elements</span></span>  
 <span data-ttu-id="3998b-161">nessuno</span><span class="sxs-lookup"><span data-stu-id="3998b-161">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3998b-162">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3998b-162">Parent Elements</span></span>  
  
|<span data-ttu-id="3998b-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="3998b-163">Element</span></span>|<span data-ttu-id="3998b-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3998b-164">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="3998b-165">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3998b-165">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3998b-166">Commenti</span><span class="sxs-lookup"><span data-stu-id="3998b-166">Remarks</span></span>  
 <span data-ttu-id="3998b-167">Le sessioni affidabili forniscono funzionalità per la messaggistica affidabile e le sessioni.</span><span class="sxs-lookup"><span data-stu-id="3998b-167">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="3998b-168">La messaggistica affidabile ritenta la comunicazione in caso di errore e consente di specificare assicurazioni del recapito quali l'arrivo nell'ordine di invio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3998b-168">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="3998b-169">Le sessioni gestiscono lo stato per i client tra le chiamate.</span><span class="sxs-lookup"><span data-stu-id="3998b-169">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="3998b-170">Questo elemento fornisce inoltre il recapito ordinato dei messaggi (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="3998b-170">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="3998b-171">Questa sessione implementata può attraversare intermediari SOAP e di trasporto.</span><span class="sxs-lookup"><span data-stu-id="3998b-171">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="3998b-172">Ogni elemento di associazione rappresenta una fase di elaborazione durante l'invio o la ricezione di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3998b-172">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="3998b-173">In fase di esecuzione gli elementi di associazione creano le channel factory e i listener necessari per compilare stack di canali in uscita e in ingresso richiesti per l'invio e la ricezione di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3998b-173">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="3998b-174">La classe `reliableSession` fornisce un livello facoltativo nello stack che può stabilire una sessione affidabile tra endpoint e configurare il comportamento di questa sessione.</span><span class="sxs-lookup"><span data-stu-id="3998b-174">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="3998b-175">Per altre informazioni, vedere [sessioni affidabili](../../../wcf/feature-details/reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="3998b-175">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3998b-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="3998b-176">Example</span></span>  
 <span data-ttu-id="3998b-177">Nell'esempio seguente è dimostrato come configurare un'associazione personalizzata con vari elementi di codifica di trasporto e messaggio, in particolare l'attivazione di sessioni affidabili, che mantiene lo stato client e specifica assicurazioni di recapito nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3998b-177">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="3998b-178">Questa funzionalità è configurata nei file di configurazione dell'applicazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="3998b-178">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="3998b-179">Nell'esempio è illustrata la configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3998b-179">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
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
  
## <a name="see-also"></a><span data-ttu-id="3998b-180">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3998b-180">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="3998b-181">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="3998b-181">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="3998b-182">Binding</span><span class="sxs-lookup"><span data-stu-id="3998b-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3998b-183">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="3998b-183">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3998b-184">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="3998b-184">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
