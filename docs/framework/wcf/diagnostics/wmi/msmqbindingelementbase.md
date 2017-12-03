---
title: MsmqBindingElementBase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b70b4b4a1529085cba8625598f56a9eece07e866
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="964f2-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="964f2-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="964f2-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="964f2-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="964f2-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="964f2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="964f2-105">Methods</span></span>  
 <span data-ttu-id="964f2-106">La classe MsmqBindingElementBase non definisce alcun metodo.</span><span class="sxs-lookup"><span data-stu-id="964f2-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="964f2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="964f2-107">Properties</span></span>  
 <span data-ttu-id="964f2-108">La classe MsmqBindingElementBase ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="964f2-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="964f2-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="964f2-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="964f2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="964f2-110">Data type: string</span></span>  
  
 <span data-ttu-id="964f2-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-112">URI che contiene il percorso della coda dei messaggi non recapitabili per ogni applicazione, in cui vengono collocati i messaggi scaduti o che non possono essere trasferiti o recapitati.</span><span class="sxs-lookup"><span data-stu-id="964f2-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="964f2-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="964f2-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="964f2-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="964f2-114">Data type: string</span></span>  
  
 <span data-ttu-id="964f2-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-116">Valore di enumerazione che indica il tipo di coda dei messaggi non recapitabili da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="964f2-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="964f2-117">Durevole</span><span class="sxs-lookup"><span data-stu-id="964f2-117">Durable</span></span>  
 <span data-ttu-id="964f2-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="964f2-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="964f2-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-120">Valore che indica se i messaggi elaborati da questa associazione sono durevoli o volatili.</span><span class="sxs-lookup"><span data-stu-id="964f2-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="964f2-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="964f2-121">ExactlyOnce</span></span>  
 <span data-ttu-id="964f2-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="964f2-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="964f2-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-124">Valore booleano che indica se i messaggi elaborati da questa associazione vengono ricevuti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="964f2-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="964f2-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="964f2-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="964f2-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="964f2-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="964f2-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-128">Numero massimo di cicli di ripetizione dei tentativi di recapito dei messaggi all'applicazione ricevente.</span><span class="sxs-lookup"><span data-stu-id="964f2-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="964f2-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="964f2-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="964f2-130">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="964f2-130">Data type: string</span></span>  
  
 <span data-ttu-id="964f2-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-132">Impostazioni per la gestione dei messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="964f2-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="964f2-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="964f2-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="964f2-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="964f2-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="964f2-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-136">Numero massimo di tentativi immediati su un messaggio letto dalla coda dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="964f2-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="964f2-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="964f2-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="964f2-138">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="964f2-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="964f2-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-140">Valore che indica l'intervallo di tempo tra i cicli di ripetizione dei tentativi di recapitare un messaggio che è impossibile recapitare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="964f2-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="964f2-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="964f2-141">TimeToLive</span></span>  
 <span data-ttu-id="964f2-142">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="964f2-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="964f2-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-144">Valore che indica per quanto tempo i messaggi elaborati da questa associazione possono rimanere nella coda prima di scadere.</span><span class="sxs-lookup"><span data-stu-id="964f2-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="964f2-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="964f2-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="964f2-146">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="964f2-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="964f2-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-148">Valore booleano che indica se i messaggi elaborati da questa associazione devono essere tracciati.</span><span class="sxs-lookup"><span data-stu-id="964f2-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="964f2-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="964f2-149">UseSourceJournal</span></span>  
 <span data-ttu-id="964f2-150">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="964f2-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="964f2-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="964f2-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="964f2-152">Valore booleano che indica se le copie dei messaggi elaborati da questa associazione devono essere archiviate nella coda journal di origine.</span><span class="sxs-lookup"><span data-stu-id="964f2-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964f2-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="964f2-153">Requirements</span></span>  
  
|<span data-ttu-id="964f2-154">MOF</span><span class="sxs-lookup"><span data-stu-id="964f2-154">MOF</span></span>|<span data-ttu-id="964f2-155">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="964f2-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="964f2-156">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="964f2-156">Namespace</span></span>|<span data-ttu-id="964f2-157">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="964f2-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="964f2-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="964f2-158">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>
