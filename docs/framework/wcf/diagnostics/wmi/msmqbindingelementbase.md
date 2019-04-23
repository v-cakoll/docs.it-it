---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 1df4b32feda246a536183a42ac11b113bc4bb259
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768397"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="ef654-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="ef654-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="ef654-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="ef654-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef654-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef654-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ef654-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ef654-105">Methods</span></span>  
 <span data-ttu-id="ef654-106">La classe MsmqBindingElementBase non definisce alcun metodo.</span><span class="sxs-lookup"><span data-stu-id="ef654-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ef654-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ef654-107">Properties</span></span>  
 <span data-ttu-id="ef654-108">La classe MsmqBindingElementBase ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef654-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="ef654-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="ef654-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="ef654-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ef654-110">Data type: string</span></span>  
  
 <span data-ttu-id="ef654-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-112">URI che contiene il percorso della coda dei messaggi non recapitabili per ogni applicazione, in cui vengono collocati i messaggi scaduti o che non possono essere trasferiti o recapitati.</span><span class="sxs-lookup"><span data-stu-id="ef654-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="ef654-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="ef654-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="ef654-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ef654-114">Data type: string</span></span>  
  
 <span data-ttu-id="ef654-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-116">Valore di enumerazione che indica il tipo di coda dei messaggi non recapitabili da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ef654-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="ef654-117">Durevole</span><span class="sxs-lookup"><span data-stu-id="ef654-117">Durable</span></span>  
 <span data-ttu-id="ef654-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ef654-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef654-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-120">Valore che indica se i messaggi elaborati da questa associazione sono durevoli o volatili.</span><span class="sxs-lookup"><span data-stu-id="ef654-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="ef654-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="ef654-121">ExactlyOnce</span></span>  
 <span data-ttu-id="ef654-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ef654-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef654-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-124">Valore booleano che indica se i messaggi elaborati da questa associazione vengono ricevuti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ef654-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="ef654-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="ef654-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="ef654-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="ef654-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="ef654-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-128">Numero massimo di cicli di ripetizione dei tentativi di recapito dei messaggi all'applicazione ricevente.</span><span class="sxs-lookup"><span data-stu-id="ef654-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="ef654-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="ef654-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="ef654-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ef654-130">Data type: string</span></span>  
  
 <span data-ttu-id="ef654-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-132">Impostazioni per la gestione dei messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="ef654-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="ef654-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="ef654-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="ef654-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="ef654-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="ef654-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-136">Numero massimo di tentativi immediati su un messaggio letto dalla coda dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ef654-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="ef654-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="ef654-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="ef654-138">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="ef654-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="ef654-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-140">Valore che indica l'intervallo di tempo tra i cicli di ripetizione dei tentativi di recapitare un messaggio che è impossibile recapitare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="ef654-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="ef654-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="ef654-141">TimeToLive</span></span>  
 <span data-ttu-id="ef654-142">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="ef654-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="ef654-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-144">Valore che indica per quanto tempo i messaggi elaborati da questa associazione possono rimanere nella coda prima di scadere.</span><span class="sxs-lookup"><span data-stu-id="ef654-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="ef654-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="ef654-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="ef654-146">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ef654-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef654-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-148">Valore booleano che indica se i messaggi elaborati da questa associazione devono essere tracciati.</span><span class="sxs-lookup"><span data-stu-id="ef654-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="ef654-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="ef654-149">UseSourceJournal</span></span>  
 <span data-ttu-id="ef654-150">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ef654-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="ef654-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="ef654-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef654-152">Valore booleano che indica se le copie dei messaggi elaborati da questa associazione devono essere archiviate nella coda journal di origine.</span><span class="sxs-lookup"><span data-stu-id="ef654-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef654-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef654-153">Requirements</span></span>  
  
|<span data-ttu-id="ef654-154">MOF</span><span class="sxs-lookup"><span data-stu-id="ef654-154">MOF</span></span>|<span data-ttu-id="ef654-155">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ef654-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ef654-156">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ef654-156">Namespace</span></span>|<span data-ttu-id="ef654-157">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ef654-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef654-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef654-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
