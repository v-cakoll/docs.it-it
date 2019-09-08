---
title: Endpoint
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795903"
---
# <a name="endpoint"></a><span data-ttu-id="dc0c4-102">Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc0c4-102">Endpoint</span></span>
<span data-ttu-id="dc0c4-103">Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc0c4-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc0c4-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="dc0c4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dc0c4-105">Methods</span></span>  
 <span data-ttu-id="dc0c4-106">La classe Endpoint definisce il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="dc0c4-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="dc0c4-107">Method</span></span>|<span data-ttu-id="dc0c4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc0c4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc0c4-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="dc0c4-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="dc0c4-110">Recupera il nome dell'istanza del contatore delle prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="dc0c4-111">Properties</span><span class="sxs-lookup"><span data-stu-id="dc0c4-111">Properties</span></span>  
 <span data-ttu-id="dc0c4-112">La classe Endpoint ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc0c4-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="dc0c4-113">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="dc0c4-113">Address</span></span>  
 <span data-ttu-id="dc0c4-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-114">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-116">URI che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="dc0c4-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="dc0c4-117">AddressHeaders</span></span>  
 <span data-ttu-id="dc0c4-118">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="dc0c4-118">Data type: string array</span></span>  
  
 <span data-ttu-id="dc0c4-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-120">Raccolta di intestazioni di indirizzo associato a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="dc0c4-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="dc0c4-121">AddressIdentity</span></span>  
 <span data-ttu-id="dc0c4-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-122">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-124">Identità dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="dc0c4-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="dc0c4-125">AppDomainId</span></span>  
 <span data-ttu-id="dc0c4-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="dc0c4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="dc0c4-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-128">ID del dominio applicazione che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="dc0c4-129">comportamenti</span><span class="sxs-lookup"><span data-stu-id="dc0c4-129">Behaviors</span></span>  
 <span data-ttu-id="dc0c4-130">Tipo di dati: Matrice di comportamenti</span><span class="sxs-lookup"><span data-stu-id="dc0c4-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="dc0c4-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-132">Raccolta dei comportamenti implementati da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="dc0c4-133">Associazione</span><span class="sxs-lookup"><span data-stu-id="dc0c4-133">Binding</span></span>  
 <span data-ttu-id="dc0c4-134">Tipo di dati: Associazione</span><span class="sxs-lookup"><span data-stu-id="dc0c4-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="dc0c4-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-136">Associazione usata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="dc0c4-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="dc0c4-137">ContractName</span></span>  
 <span data-ttu-id="dc0c4-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-138">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-140">Stringa che specifica il contratto che viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="dc0c4-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="dc0c4-141">CounterInstanceName</span></span>  
 <span data-ttu-id="dc0c4-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-142">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-144">Nome dell'istanza del contatore delle prestazioni dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="dc0c4-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="dc0c4-145">ListenUri</span></span>  
 <span data-ttu-id="dc0c4-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-146">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-148">URI sul quale resta in attesa l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="dc0c4-149">Name</span><span class="sxs-lookup"><span data-stu-id="dc0c4-149">Name</span></span>  
 <span data-ttu-id="dc0c4-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc0c4-150">Data type: string</span></span>  
  
 <span data-ttu-id="dc0c4-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-152">Nome univoco di questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="dc0c4-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="dc0c4-153">ProcessId</span></span>  
 <span data-ttu-id="dc0c4-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="dc0c4-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="dc0c4-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-156">ID del processo che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="dc0c4-157">ref</span><span class="sxs-lookup"><span data-stu-id="dc0c4-157">ref</span></span>  
 <span data-ttu-id="dc0c4-158">Tipo di dati: Contratto</span><span class="sxs-lookup"><span data-stu-id="dc0c4-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="dc0c4-159">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc0c4-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc0c4-160">Contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0c4-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc0c4-161">Requirements</span></span>  
  
|<span data-ttu-id="dc0c4-162">MOF</span><span class="sxs-lookup"><span data-stu-id="dc0c4-162">MOF</span></span>|<span data-ttu-id="dc0c4-163">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dc0c4-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dc0c4-164">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="dc0c4-164">Namespace</span></span>|<span data-ttu-id="dc0c4-165">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc0c4-165">Defined in root\ServiceModel</span></span>|
