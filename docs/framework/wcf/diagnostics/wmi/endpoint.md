---
title: Endpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bcb02ae01d66830d9bfd486c5ae3941c45c2a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint"></a><span data-ttu-id="d309c-102">Endpoint</span><span class="sxs-lookup"><span data-stu-id="d309c-102">Endpoint</span></span>
<span data-ttu-id="d309c-103">Endpoint</span><span class="sxs-lookup"><span data-stu-id="d309c-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d309c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d309c-104">Syntax</span></span>  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d309c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d309c-105">Methods</span></span>  
 <span data-ttu-id="d309c-106">La classe Endpoint definisce il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="d309c-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="d309c-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="d309c-107">Method</span></span>|<span data-ttu-id="d309c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d309c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d309c-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d309c-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="d309c-110">Recupera il nome dell'istanza del contatore delle prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d309c-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="d309c-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d309c-111">Properties</span></span>  
 <span data-ttu-id="d309c-112">La classe Endpoint ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d309c-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="d309c-113">Address</span><span class="sxs-lookup"><span data-stu-id="d309c-113">Address</span></span>  
 <span data-ttu-id="d309c-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-114">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-116">URI che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="d309c-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="d309c-117">AddressHeaders</span></span>  
 <span data-ttu-id="d309c-118">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="d309c-118">Data type: string array</span></span>  
  
 <span data-ttu-id="d309c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-120">Raccolta di intestazioni di indirizzo associato a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="d309c-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="d309c-121">AddressIdentity</span></span>  
 <span data-ttu-id="d309c-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-122">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-124">Identità dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="d309c-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="d309c-125">AppDomainId</span></span>  
 <span data-ttu-id="d309c-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d309c-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="d309c-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-128">ID del dominio applicazione che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="d309c-129">Comportamenti</span><span class="sxs-lookup"><span data-stu-id="d309c-129">Behaviors</span></span>  
 <span data-ttu-id="d309c-130">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="d309c-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="d309c-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-132">Raccolta dei comportamenti implementati da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="d309c-133">Binding</span><span class="sxs-lookup"><span data-stu-id="d309c-133">Binding</span></span>  
 <span data-ttu-id="d309c-134">Tipo di dati: associazione</span><span class="sxs-lookup"><span data-stu-id="d309c-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="d309c-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-136">Associazione usata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="d309c-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="d309c-137">ContractName</span></span>  
 <span data-ttu-id="d309c-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-138">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-140">Stringa che specifica il contratto che viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="d309c-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d309c-141">CounterInstanceName</span></span>  
 <span data-ttu-id="d309c-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-142">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-144">Nome dell'istanza del contatore delle prestazioni dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="d309c-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="d309c-145">ListenUri</span></span>  
 <span data-ttu-id="d309c-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-146">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-148">URI sul quale resta in attesa l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d309c-149">Nome</span><span class="sxs-lookup"><span data-stu-id="d309c-149">Name</span></span>  
 <span data-ttu-id="d309c-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="d309c-150">Data type: string</span></span>  
  
 <span data-ttu-id="d309c-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-152">Nome univoco di questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d309c-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d309c-153">ProcessId</span></span>  
 <span data-ttu-id="d309c-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="d309c-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="d309c-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-156">ID del processo che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="d309c-157">ref</span><span class="sxs-lookup"><span data-stu-id="d309c-157">ref</span></span>  
 <span data-ttu-id="d309c-158">Tipo di dati: contratto</span><span class="sxs-lookup"><span data-stu-id="d309c-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="d309c-159">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d309c-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d309c-160">Contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d309c-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d309c-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d309c-161">Requirements</span></span>  
  
|<span data-ttu-id="d309c-162">MOF</span><span class="sxs-lookup"><span data-stu-id="d309c-162">MOF</span></span>|<span data-ttu-id="d309c-163">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d309c-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d309c-164">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d309c-164">Namespace</span></span>|<span data-ttu-id="d309c-165">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d309c-165">Defined in root\ServiceModel</span></span>|
