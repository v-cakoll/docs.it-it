---
title: Service
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7b631ede7bd011a92003dc5f6083c1c427d990e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="service"></a><span data-ttu-id="a0833-102">Service</span><span class="sxs-lookup"><span data-stu-id="a0833-102">Service</span></span>
<span data-ttu-id="a0833-103">Service</span><span class="sxs-lookup"><span data-stu-id="a0833-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0833-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0833-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a0833-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a0833-105">Methods</span></span>  
 <span data-ttu-id="a0833-106">La classe Service non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a0833-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a0833-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a0833-107">Properties</span></span>  
 <span data-ttu-id="a0833-108">La classe Service presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0833-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="a0833-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="a0833-109">BaseAddresses</span></span>  
 <span data-ttu-id="a0833-110">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="a0833-110">Data type: string array</span></span>  
  
 <span data-ttu-id="a0833-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-112">Indirizzi di base utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="a0833-113">comportamenti</span><span class="sxs-lookup"><span data-stu-id="a0833-113">Behaviors</span></span>  
 <span data-ttu-id="a0833-114">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="a0833-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="a0833-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-116">Comportamenti associati al servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="a0833-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="a0833-117">ConfigurationName</span></span>  
 <span data-ttu-id="a0833-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a0833-118">Data type: string</span></span>  
  
 <span data-ttu-id="a0833-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0833-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="a0833-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="a0833-121">CounterInstanceName</span></span>  
 <span data-ttu-id="a0833-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a0833-122">Data type: string</span></span>  
  
 <span data-ttu-id="a0833-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-124">Nome dell'istanza del contatore delle prestazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="a0833-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a0833-125">DistinguishedName</span></span>  
 <span data-ttu-id="a0833-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a0833-126">Data type: string</span></span>  
  
 <span data-ttu-id="a0833-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-128">Nome del servizio all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a0833-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="a0833-129">Estensioni</span><span class="sxs-lookup"><span data-stu-id="a0833-129">Extensions</span></span>  
 <span data-ttu-id="a0833-130">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="a0833-130">Data type: string array</span></span>  
  
 <span data-ttu-id="a0833-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-132">Contesti dell'istanza per le estensioni dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="a0833-133">Metadati</span><span class="sxs-lookup"><span data-stu-id="a0833-133">Metadata</span></span>  
 <span data-ttu-id="a0833-134">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="a0833-134">Data type: string array</span></span>  
  
 <span data-ttu-id="a0833-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-136">Impostazioni dei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a0833-137">nome</span><span class="sxs-lookup"><span data-stu-id="a0833-137">Name</span></span>  
 <span data-ttu-id="a0833-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a0833-138">Data type: string</span></span>  
  
 <span data-ttu-id="a0833-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-140">Nome univoco del servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="a0833-141">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a0833-141">Namespace</span></span>  
 <span data-ttu-id="a0833-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="a0833-142">Data type: string</span></span>  
  
 <span data-ttu-id="a0833-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-144">Spazio dei nomi del servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="a0833-145">Opened</span><span class="sxs-lookup"><span data-stu-id="a0833-145">Opened</span></span>  
 <span data-ttu-id="a0833-146">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="a0833-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="a0833-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-148">Ora in cui il servizio è stato aperto.</span><span class="sxs-lookup"><span data-stu-id="a0833-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="a0833-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="a0833-149">OutgoingChannels</span></span>  
 <span data-ttu-id="a0833-150">Tipo di dati: matrice di Channel</span><span class="sxs-lookup"><span data-stu-id="a0833-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="a0833-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-152">Canali in uscita dall'istanza di servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="a0833-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="a0833-153">ProcessId</span></span>  
 <span data-ttu-id="a0833-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="a0833-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="a0833-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="a0833-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a0833-156">Id del processo che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="a0833-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0833-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0833-157">Requirements</span></span>  
  
|<span data-ttu-id="a0833-158">MOF</span><span class="sxs-lookup"><span data-stu-id="a0833-158">MOF</span></span>|<span data-ttu-id="a0833-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a0833-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a0833-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a0833-160">Namespace</span></span>|<span data-ttu-id="a0833-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0833-161">Defined in root\ServiceModel</span></span>|
