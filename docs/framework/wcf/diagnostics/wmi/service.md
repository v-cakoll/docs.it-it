---
title: Service
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374211"
---
# <a name="service"></a><span data-ttu-id="d4860-102">Service</span><span class="sxs-lookup"><span data-stu-id="d4860-102">Service</span></span>
<span data-ttu-id="d4860-103">Service</span><span class="sxs-lookup"><span data-stu-id="d4860-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4860-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4860-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="d4860-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d4860-105">Methods</span></span>  
 <span data-ttu-id="d4860-106">La classe Service non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="d4860-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4860-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d4860-107">Properties</span></span>  
 <span data-ttu-id="d4860-108">La classe Service presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4860-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="d4860-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="d4860-109">BaseAddresses</span></span>  
 <span data-ttu-id="d4860-110">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="d4860-110">Data type: string array</span></span>  
  
 <span data-ttu-id="d4860-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-112">Indirizzi di base utilizzati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="d4860-113">comportamenti</span><span class="sxs-lookup"><span data-stu-id="d4860-113">Behaviors</span></span>  
 <span data-ttu-id="d4860-114">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="d4860-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="d4860-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-116">Comportamenti associati al servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="d4860-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d4860-117">ConfigurationName</span></span>  
 <span data-ttu-id="d4860-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d4860-118">Data type: string</span></span>  
  
 <span data-ttu-id="d4860-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4860-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="d4860-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d4860-121">CounterInstanceName</span></span>  
 <span data-ttu-id="d4860-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d4860-122">Data type: string</span></span>  
  
 <span data-ttu-id="d4860-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-124">Nome dell'istanza del contatore delle prestazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="d4860-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="d4860-125">DistinguishedName</span></span>  
 <span data-ttu-id="d4860-126">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d4860-126">Data type: string</span></span>  
  
 <span data-ttu-id="d4860-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-128">Nome del servizio all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d4860-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="d4860-129">Estensioni</span><span class="sxs-lookup"><span data-stu-id="d4860-129">Extensions</span></span>  
 <span data-ttu-id="d4860-130">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="d4860-130">Data type: string array</span></span>  
  
 <span data-ttu-id="d4860-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-132">Contesti dell'istanza per le estensioni dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="d4860-133">Metadati</span><span class="sxs-lookup"><span data-stu-id="d4860-133">Metadata</span></span>  
 <span data-ttu-id="d4860-134">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="d4860-134">Data type: string array</span></span>  
  
 <span data-ttu-id="d4860-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-136">Impostazioni dei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d4860-137">nome</span><span class="sxs-lookup"><span data-stu-id="d4860-137">Name</span></span>  
 <span data-ttu-id="d4860-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d4860-138">Data type: string</span></span>  
  
 <span data-ttu-id="d4860-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-140">Nome univoco del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="d4860-141">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d4860-141">Namespace</span></span>  
 <span data-ttu-id="d4860-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d4860-142">Data type: string</span></span>  
  
 <span data-ttu-id="d4860-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-144">Spazio dei nomi del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="d4860-145">Opened</span><span class="sxs-lookup"><span data-stu-id="d4860-145">Opened</span></span>  
 <span data-ttu-id="d4860-146">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="d4860-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="d4860-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-148">Ora in cui il servizio è stato aperto.</span><span class="sxs-lookup"><span data-stu-id="d4860-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="d4860-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="d4860-149">OutgoingChannels</span></span>  
 <span data-ttu-id="d4860-150">Tipo di dati: matrice di Channel</span><span class="sxs-lookup"><span data-stu-id="d4860-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="d4860-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-152">Canali in uscita dall'istanza di servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d4860-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d4860-153">ProcessId</span></span>  
 <span data-ttu-id="d4860-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d4860-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="d4860-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4860-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4860-156">Id del processo che ospita il servizio.</span><span class="sxs-lookup"><span data-stu-id="d4860-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4860-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4860-157">Requirements</span></span>  
  
|<span data-ttu-id="d4860-158">MOF</span><span class="sxs-lookup"><span data-stu-id="d4860-158">MOF</span></span>|<span data-ttu-id="d4860-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d4860-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4860-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d4860-160">Namespace</span></span>|<span data-ttu-id="d4860-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4860-161">Defined in root\ServiceModel</span></span>|
