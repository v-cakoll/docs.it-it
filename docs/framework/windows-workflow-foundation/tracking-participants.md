---
title: Partecipanti del rilevamento
ms.date: 03/30/2017
ms.assetid: f13e360c-eeb7-4a49-98a0-8f6a52d64f68
ms.openlocfilehash: a033b65125a562307c6247eeda93dcacb31f5382
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837649"
---
# <a name="tracking-participants"></a><span data-ttu-id="1ef43-102">Partecipanti del rilevamento</span><span class="sxs-lookup"><span data-stu-id="1ef43-102">Tracking Participants</span></span>
<span data-ttu-id="1ef43-103">I partecipanti del rilevamento sono punti di estensibilità che consentono a uno sviluppatore di flussi di lavoro di accedere a oggetti <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> e di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="1ef43-103">Tracking participants are extensibility points that allow a workflow developer to access <xref:System.Activities.Tracking.InteropTrackingRecord.TrackingRecord%2A> objects and process them.</span></span> <span data-ttu-id="1ef43-104">In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] viene fornito un partecipante del rilevamento standard che scrive record di rilevamento come eventi ETW (Event Tracing for Windows).</span><span class="sxs-lookup"><span data-stu-id="1ef43-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="1ef43-105">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1ef43-105">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="tracking-participants"></a><span data-ttu-id="1ef43-106">Partecipanti del rilevamento</span><span class="sxs-lookup"><span data-stu-id="1ef43-106">Tracking Participants</span></span>  
 <span data-ttu-id="1ef43-107">L'infrastruttura di rilevamento consente l'applicazione di un filtro ai record di rilevamento in uscita in modo che un partecipante possa sottoscrivere un subset dei record.</span><span class="sxs-lookup"><span data-stu-id="1ef43-107">The tracking infrastructure allows the application of a filter on the outgoing tracking records such that a participant can subscribe to a subset of the records.</span></span> <span data-ttu-id="1ef43-108">Il meccanismo di applicazione di un filtro avviene tramite un profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1ef43-108">The mechanism to apply a filter is through a tracking profile.</span></span>  
  
 <span data-ttu-id="1ef43-109">Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] fornisce un partecipante del rilevamento che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="1ef43-109">Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides a tracking participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="1ef43-110">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1ef43-110">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="1ef43-111">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="1ef43-111">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="1ef43-112">L'esempio SDK per il rilevamento basato su ETW rappresenta un buon metodo per acquisire familiarità con il rilevamento WF tramite il partecipante del rilevamento basato su ETW.</span><span class="sxs-lookup"><span data-stu-id="1ef43-112">The SDK sample for ETW-based tracking is a good way to get familiar with WF tracking using the ETW-based tracking participant.</span></span>  
  
## <a name="etw-tracking-participant"></a><span data-ttu-id="1ef43-113">Partecipante del rilevamento ETW</span><span class="sxs-lookup"><span data-stu-id="1ef43-113">ETW Tracking Participant</span></span>  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="1ef43-114">include un partecipante del rilevamento ETW mediante il quale vengono scritti i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="1ef43-114">includes an ETW Tracking Participant that writes the tracking records to an ETW session.</span></span> <span data-ttu-id="1ef43-115">Questa operazione viene eseguita in modo molto efficiente con un impatto minimo sulle prestazioni dell'applicazione o sulla velocità effettiva del server.</span><span class="sxs-lookup"><span data-stu-id="1ef43-115">This is done in a very efficient manner with minimal impact to the application’s performance or to the server’s throughput.</span></span> <span data-ttu-id="1ef43-116">Un vantaggio associato all'utilizzo del partecipante del rilevamento ETW standard è la possibilità di visualizzare i record di rilevamento ricevuti con altri registri applicazioni e di sistema nel Visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="1ef43-116">An advantage of using the standard ETW tracking participant is that the tracking records it receives can be viewed with the other application and system logs in the Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="1ef43-117">Il partecipante del rilevamento ETW standard viene configurato nel file Web.config come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1ef43-117">The standard ETW tracking participant is configured in the Web.config file as shown in the following example.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
   <tracking>  
      <profiles>  
        <trackingProfile name="Sample Tracking Profile">  
        ….  
       </trackingProfile>  
      </profiles>  
    </tracking>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="1ef43-118">Se non è specificato un nome per `trackingProfile`, ad esempio `<etwTracking/>` o `<etwTracking profileName=""/>`, viene usato il profilo di rilevamento predefinito installato con [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] nel file Machine.config.</span><span class="sxs-lookup"><span data-stu-id="1ef43-118">If a `trackingProfile` name is not specified, such as just `<etwTracking/>` or `<etwTracking profileName=""/>`, then the default tracking profile installed with the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in the Machine.config file is used.</span></span>  
  
 <span data-ttu-id="1ef43-119">Il profilo di rilevamento predefinito disponibile in tale file consente di sottoscrivere record ed errori di istanze di flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ef43-119">In the Machine.config file, the default tracking profile subscribes to workflow instance records and faults.</span></span>  
  
 <span data-ttu-id="1ef43-120">In ETW gli eventi vengono scritti nella sessione ETW tramite un ID provider.</span><span class="sxs-lookup"><span data-stu-id="1ef43-120">In ETW, events are written to the ETW session through a provider ID.</span></span> <span data-ttu-id="1ef43-121">L'ID provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione relativa alla diagnostica del file Web.config (in `<system.serviceModel><diagnostics>`).</span><span class="sxs-lookup"><span data-stu-id="1ef43-121">The provider ID that the ETW tracking participant uses for writing the tracking records to ETW is defined in the diagnostics section of the Web.config file (under `<system.serviceModel><diagnostics>`).</span></span> <span data-ttu-id="1ef43-122">Per impostazione predefinita, il partecipante del rilevamento ETW usa un ID provider predefinito quando non ne è stato specificato uno, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1ef43-122">By default, the ETW tracking participant uses a default provider ID when one has not been specified, as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
        <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />  
```  
  
 <span data-ttu-id="1ef43-123">Nell'illustrazione seguente viene mostrato il flusso di dati di rilevamento tramite il partecipante del rilevamento ETW.</span><span class="sxs-lookup"><span data-stu-id="1ef43-123">The following illustration shows the flow of tracking data through the ETW tracking participant.</span></span> <span data-ttu-id="1ef43-124">Una volta che i dati di rilevamento hanno raggiunto la sessione ETW, è possibile accedervi in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="1ef43-124">Once the tracking data reaches the ETW session, it can be accessed in a number of ways.</span></span> <span data-ttu-id="1ef43-125">Uno dei modi più utili per accedere a questi eventi è tramite il Visualizzatore eventi, uno strumento Windows comune usato per la visualizzazione di log e di tracce da applicazioni e servizi.</span><span class="sxs-lookup"><span data-stu-id="1ef43-125">One of the most useful ways to access these events is through Event Viewer, a common Windows tool used for viewing logs and traces from applications and services.</span></span>  
  
 ![Flusso dei dati di rilevamento tramite il provider di rilevamento ETW.](./media/tracking-participants/tracking-data-event-tracing-windows-provider.gif)  
  
## <a name="tracking-participant-event-data"></a><span data-ttu-id="1ef43-127">Dati evento del partecipante del rilevamento</span><span class="sxs-lookup"><span data-stu-id="1ef43-127">Tracking Participant Event Data</span></span>  
 <span data-ttu-id="1ef43-128">Un partecipante del rilevamento serializza i dati evento rilevati in una sessione ETW nel formato di un evento per il record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1ef43-128">A tracking participant serializes tracked event data to an ETW session in the format of one event per tracking record.</span></span>  <span data-ttu-id="1ef43-129">Un evento viene identificato usando un ID compreso nell'intervallo tra 100 e 199.</span><span class="sxs-lookup"><span data-stu-id="1ef43-129">An event is identified using an ID within the range of 100 through 199.</span></span> <span data-ttu-id="1ef43-130">Per le definizioni dei record degli eventi di rilevamento creati da un partecipante del rilevamento, vedere l'argomento di [riferimento sugli eventi](tracking-events-reference.md) di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="1ef43-130">For definitions of the tracking event records emitted by a tracking participant, see the [Tracking Events Reference](tracking-events-reference.md) topic.</span></span>  
  
 <span data-ttu-id="1ef43-131">La dimensione di un evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW, a seconda di quale dimensione è minore.</span><span class="sxs-lookup"><span data-stu-id="1ef43-131">The size of an ETW event is limited by the ETW buffer size, or the by the maximum payload for an ETW event, whichever value is smaller.</span></span> <span data-ttu-id="1ef43-132">Se la dimensione dell'evento supera entrambi questi limiti ETW, l'evento viene troncato e il relativo contenuto rimosso in maniera arbitraria.</span><span class="sxs-lookup"><span data-stu-id="1ef43-132">If the size of the event exceeds either of these ETW limits, the event is truncated and its content removed in an arbitrary manner.</span></span> <span data-ttu-id="1ef43-133">Variabili, argomenti, annotazioni e dati personalizzati non vengono rimossi in modo selettivo.</span><span class="sxs-lookup"><span data-stu-id="1ef43-133">Variables, arguments, annotations and custom data are not selectively removed.</span></span> <span data-ttu-id="1ef43-134">In caso di troncamento, tutti gli elementi vengono troncati indipendentemente dal valore che ha causato il superamento del limite ETW della dimensione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1ef43-134">In the case of truncation, all of these are truncated regardless of the value that caused the event size to exceed the ETW limit.</span></span>  <span data-ttu-id="1ef43-135">I dati rimossi vengono sostituiti con `<item>..<item>`.</span><span class="sxs-lookup"><span data-stu-id="1ef43-135">The removed data is replaced with `<item>..<item>`.</span></span>  
  
 <span data-ttu-id="1ef43-136">I tipi complessi in variabili, argomenti ed elementi di dati personalizzati vengono serializzati nel record dell'evento ETW usando la classe <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-136">Complex types in variables, arguments, and custom data items are serialized to the ETW event record using the <xref:System.Runtime.Serialization.NetDataContractSerializer> class.</span></span> <span data-ttu-id="1ef43-137">Questa classe include informazioni sul tipo CLR nel flusso XML serializzato.</span><span class="sxs-lookup"><span data-stu-id="1ef43-137">This class includes CLR-type information in the serialized XML steam.</span></span>  
  
 <span data-ttu-id="1ef43-138">Il troncamento di dati payload dovuto ai limiti ETW può comportare l'invio di record di rilevamento duplicati a una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="1ef43-138">Truncation of payload data due to ETW limits can result in duplicate tracking records being sent to an ETW session.</span></span> <span data-ttu-id="1ef43-139">Questa situazione si può verificare se più sessioni restano in ascolto di eventi. Le sessioni presentano limiti di payload differenti per gli eventi.</span><span class="sxs-lookup"><span data-stu-id="1ef43-139">This can occur if more than one session is listening for the events and the sessions have different payload limits for the events.</span></span>  
  
 <span data-ttu-id="1ef43-140">L'evento della sessione con il limite inferiore può essere troncato.</span><span class="sxs-lookup"><span data-stu-id="1ef43-140">For  the session with the lower limit the event may be truncated.</span></span> <span data-ttu-id="1ef43-141">Il partecipante del rilevamento ETW non è informato sul numero di sessioni in attesa di eventi. Se un evento viene troncato per una sessione, il partecipante ETW ritenta l'invio dell'evento una volta.</span><span class="sxs-lookup"><span data-stu-id="1ef43-141">The ETW tracking participant does not have any knowledge of the number of sessions listening for the events; if an event is truncated for a session then the ETW participant retries sending the event once.</span></span> <span data-ttu-id="1ef43-142">In questo caso la sessione configurata per accettare una dimensione del payload maggiore otterrà l'evento due volte (l'evento non troncato e quello troncato).</span><span class="sxs-lookup"><span data-stu-id="1ef43-142">In this case the session that is configured to accept a larger payload size will get the event twice (the non-truncated and truncated event).</span></span> <span data-ttu-id="1ef43-143">La duplicazione può essere evitata configurando tutte le sessioni ETW con gli stessi limiti di dimensione del buffer.</span><span class="sxs-lookup"><span data-stu-id="1ef43-143">Duplication can be prevented by configuring all the ETW sessions with same buffer size limits.</span></span>  
  
## <a name="accessing-tracking-data-from-an-etw-participant-in-the-event-viewer"></a><span data-ttu-id="1ef43-144">Accesso ai dati di rilevamento da un partecipante ETW nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="1ef43-144">Accessing Tracking Data from an ETW Participant in the Event Viewer</span></span>  
 <span data-ttu-id="1ef43-145">L'accesso agli eventi scritti in una sessione ETW dal partecipante del rilevamento ETW può essere eseguito tramite il Visualizzatore eventi (in caso di utilizzo dell'ID provider predefinito).</span><span class="sxs-lookup"><span data-stu-id="1ef43-145">Events that are written to an ETW session by the ETW tracking participant can be accessed through the Event Viewer (when using the default provider ID).</span></span> <span data-ttu-id="1ef43-146">In questo modo è possibile visualizzare rapidamente i record di rilevamento creati dal flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ef43-146">This allows for rapidly viewing of tracking records that have been emitted by the workflow.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ef43-147">Gli eventi del record di rilevamento creati in una sessione ETW usano gli ID evento compresi nell'intervallo tra 100 e 199.</span><span class="sxs-lookup"><span data-stu-id="1ef43-147">Tracking record events emitted to an ETW session use event IDs in the range of 100 through 199.</span></span>  
  
#### <a name="to-enable-viewing-the-tracking-records-in-event-viewer"></a><span data-ttu-id="1ef43-148">Per abilitare la visualizzazione dei record di rilevamento nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="1ef43-148">To enable viewing the Tracking Records in Event Viewer</span></span>  
  
1. <span data-ttu-id="1ef43-149">Avviare il Visualizzatore eventi (EVENTVWR.EXE).</span><span class="sxs-lookup"><span data-stu-id="1ef43-149">Start the Event Viewer (EVENTVWR.EXE)</span></span>  
  
2. <span data-ttu-id="1ef43-150">Selezionare **Visualizzatore eventi, registri applicazioni e servizi, Microsoft, Windows, server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="1ef43-150">Select **Event Viewer, Applications and Services Logs, Microsoft, Windows, Application Server-Applications**.</span></span>  
  
3. <span data-ttu-id="1ef43-151">Fare clic con il pulsante destro del mouse e assicurarsi che visualizza **, Mostra log analitici e di debug** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="1ef43-151">Right-click and ensure that **View, Show Analytic and Debug logs** is selected.</span></span> <span data-ttu-id="1ef43-152">In caso contrario, selezionarlo in modo che accanto venga visualizzato il segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="1ef43-152">If not, select it so the check mark appears next to it.</span></span> <span data-ttu-id="1ef43-153">Verranno visualizzati i log **analitico**, **prestazioni**e **debug** .</span><span class="sxs-lookup"><span data-stu-id="1ef43-153">This displays the **Analytic**, **Perf**, and **Debug** logs.</span></span>  
  
4. <span data-ttu-id="1ef43-154">Fare clic con il pulsante destro del mouse sul log **analitico** e quindi scegliere **Abilita log**.</span><span class="sxs-lookup"><span data-stu-id="1ef43-154">Right-click the **Analytic** log and then select **Enable Log**.</span></span> <span data-ttu-id="1ef43-155">Il log sarà disponibile nel file %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl.</span><span class="sxs-lookup"><span data-stu-id="1ef43-155">The log will exist in the %SystemRoot%\System32\Winevt\Logs\Microsoft-Windows-Application Server-Applications%4Analytic.etl file.</span></span>  
  
## <a name="custom-tracking-participant"></a><span data-ttu-id="1ef43-156">Partecipante di rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="1ef43-156">Custom Tracking Participant</span></span>  
 <span data-ttu-id="1ef43-157">L'API del partecipante del rilevamento consente l'estensione del runtime di rilevamento con un partecipante del rilevamento fornito dall'utente che può includere la logica personalizzata per gestire i record di rilevamento creati dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ef43-157">The tracking participant API allows extension of the tracking runtime with a user-provided tracking participant that can include custom logic to handle tracking records emitted by the workflow runtime.</span></span> <span data-ttu-id="1ef43-158">Per scrivere un partecipante del rilevamento personalizzato, lo sviluppatore deve implementare il metodo `Track` sulla classe <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-158">To write a custom tracking participant, the developer must implement the `Track` method on the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="1ef43-159">Questo metodo viene chiamato quando un record di rilevamento viene creato dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ef43-159">This method is called when a tracking record is emitted by the workflow runtime.</span></span>  
  
 <span data-ttu-id="1ef43-160">I partecipanti del rilevamento derivano dalla classe <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-160">Tracking participants derive from the <xref:System.Activities.Tracking.TrackingParticipant> class.</span></span> <span data-ttu-id="1ef43-161">L'oggetto <xref:System.Activities.Tracking.EtwTrackingParticipant> fornito dal sistema crea una registrazione degli eventi per Windows (ETW, Event Tracking for Windows) per ogni record di rilevamento ricevuto.</span><span class="sxs-lookup"><span data-stu-id="1ef43-161">The system-provided <xref:System.Activities.Tracking.EtwTrackingParticipant> emits an Event Tracking for Windows (ETW) event for each tracking record that is received.</span></span> <span data-ttu-id="1ef43-162">Per creare un partecipante del rilevamento personalizzato, viene creata una classe derivata dall'oggetto <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-162">To create a custom tracking participant, a class is created that derives from <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="1ef43-163">Per fornire una funzionalità di rilevamento di base, eseguire l'override di <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-163">To provide basic tracking functionality, override <xref:System.Activities.Tracking.TrackingParticipant.Track%2A>.</span></span> <span data-ttu-id="1ef43-164">Il metodo <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> viene chiamato quando un record di rilevamento viene inviato dal runtime e può essere elaborato nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="1ef43-164"><xref:System.Activities.Tracking.TrackingParticipant.Track%2A> is called when a tracking record is sent by the runtime and can be processed in the desired manner.</span></span> <span data-ttu-id="1ef43-165">Nell'esempio seguente viene definita una classe del partecipante del rilevamento personalizzata che crea tutti i record di rilevamento nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="1ef43-165">In the following example, a custom tracking participant class is defined that emits all tracking records to the console window.</span></span> <span data-ttu-id="1ef43-166">È possibile implementare anche un oggetto <xref:System.Activities.Tracking.TrackingParticipant> che elabora i record di rilevamento in modo asincrono usando i relativi metodi `BeginTrack` e `EndTrack`</span><span class="sxs-lookup"><span data-stu-id="1ef43-166">You can also implement a <xref:System.Activities.Tracking.TrackingParticipant> object that processes the tracking records asynchronously using its `BeginTrack` and `EndTrack` methods</span></span>  
  
```csharp  
class ConsoleTrackingParticipant : TrackingParticipant  
{  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        if (record != null)  
        {  
            Console.WriteLine("=================================");  
            Console.WriteLine(record);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="1ef43-167">Per usare un determinato partecipante del rilevamento, registrarlo con l'istanza del flusso di lavoro che si desidera rilevare, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1ef43-167">To use a particular tracking participant, register it with the workflow instance that you want to track, as shown in the following example.</span></span>  
  
```csharp  
myInstance.Extensions.Add(new ConsoleTrackingParticipant());  
```  
  
 <span data-ttu-id="1ef43-168">Nell'esempio seguente viene creato un flusso di lavoro costituito da un'attività <xref:System.Activities.Statements.Sequence> che contiene un'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="1ef43-168">In the following example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> activity that contains a <xref:System.Activities.Statements.WriteLine> activity is created.</span></span> <span data-ttu-id="1ef43-169">L'oggetto `ConsoleTrackingParticipant` viene aggiunto alle estensioni e il flusso di lavoro viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="1ef43-169">The `ConsoleTrackingParticipant` is added to the extensions and the workflow is invoked.</span></span>  
  
```csharp  
Activity activity= new Sequence()  
{  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "Hello World."  
        }  
    }  
};  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
  
instance.Extensions.Add(new ConsoleTrackingParticipant());  
  instance.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
            {  
                Console.WriteLine("workflow instance completed, Id = " + instance.Id);  
                resetEvent.Set();  
            };  
            instance.Run();  
            Console.ReadLine();  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ef43-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ef43-170">See also</span></span>

- <span data-ttu-id="1ef43-171">[Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1ef43-171">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="1ef43-172">[Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1ef43-172">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
