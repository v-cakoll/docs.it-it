---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170224"
---
# <a name="appdomaininfo"></a><span data-ttu-id="868ad-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="868ad-102">AppDomainInfo</span></span>
<span data-ttu-id="868ad-103">Informazioni sul dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="868ad-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="868ad-104">Syntax</span></span>  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="868ad-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="868ad-105">Methods</span></span>  
 <span data-ttu-id="868ad-106">La classe AppDomainInfo non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="868ad-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="868ad-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="868ad-107">Properties</span></span>  
 <span data-ttu-id="868ad-108">La classe AppDomainInfo presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="868ad-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="868ad-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="868ad-109">AppDomainId</span></span>  
 <span data-ttu-id="868ad-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="868ad-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="868ad-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-112">ID del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="868ad-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="868ad-113">IsDefault</span></span>  
 <span data-ttu-id="868ad-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="868ad-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="868ad-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-116">Indica se il dominio applicazione è quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="868ad-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="868ad-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="868ad-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="868ad-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="868ad-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="868ad-119">Tipo di accesso: in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="868ad-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="868ad-120">Valore che specifica se i messaggi in formato non valido vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="868ad-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="868ad-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="868ad-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="868ad-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="868ad-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="868ad-123">Tipo di accesso: in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="868ad-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="868ad-124">Valore che specifica se i messaggi vengono registrati a livello di servizio (prima della crittografia e delle trasformazioni relative al trasporto).</span><span class="sxs-lookup"><span data-stu-id="868ad-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="868ad-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="868ad-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="868ad-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="868ad-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="868ad-127">Tipo di accesso: in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="868ad-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="868ad-128">Valore che specifica se i messaggi vengono registrati a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="868ad-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="868ad-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="868ad-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="868ad-130">Tipo di dati: matrice di TraceListener</span><span class="sxs-lookup"><span data-stu-id="868ad-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="868ad-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-132">Raccolta di listener di traccia in attesa sull'origine di traccia System.Wmi.MessageLogging.</span><span class="sxs-lookup"><span data-stu-id="868ad-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="868ad-133">nome</span><span class="sxs-lookup"><span data-stu-id="868ad-133">Name</span></span>  
 <span data-ttu-id="868ad-134">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="868ad-134">Data type: string</span></span>  
  
 <span data-ttu-id="868ad-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-136">Nome del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="868ad-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="868ad-137">PerformanceCounters</span></span>  
 <span data-ttu-id="868ad-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="868ad-138">Data type: string</span></span>  
  
 <span data-ttu-id="868ad-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-140">Ambito dei contatori delle prestazioni attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="868ad-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="868ad-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="868ad-141">ProcessId</span></span>  
 <span data-ttu-id="868ad-142">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="868ad-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="868ad-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-144">ID del processo.</span><span class="sxs-lookup"><span data-stu-id="868ad-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="868ad-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="868ad-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="868ad-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="868ad-146">Data type: string</span></span>  
  
 <span data-ttu-id="868ad-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-148">Percorso della configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="868ad-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="868ad-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="868ad-149">TraceLevel</span></span>  
 <span data-ttu-id="868ad-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="868ad-150">Data type: string</span></span>  
  
 <span data-ttu-id="868ad-151">Tipo di accesso: in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="868ad-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="868ad-152">Livello di traccia dell'origine di traccia di System.Wmi.</span><span class="sxs-lookup"><span data-stu-id="868ad-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="868ad-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="868ad-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="868ad-154">Tipo di dati: matrice di TraceListener</span><span class="sxs-lookup"><span data-stu-id="868ad-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="868ad-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="868ad-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="868ad-156">Raccolta di listener in attesa sull'origine di traccia System.ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="868ad-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="868ad-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="868ad-157">Requirements</span></span>  
  
|<span data-ttu-id="868ad-158">MOF</span><span class="sxs-lookup"><span data-stu-id="868ad-158">MOF</span></span>|<span data-ttu-id="868ad-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="868ad-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="868ad-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="868ad-160">Namespace</span></span>|<span data-ttu-id="868ad-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="868ad-161">Defined in root\ServiceModel</span></span>|
