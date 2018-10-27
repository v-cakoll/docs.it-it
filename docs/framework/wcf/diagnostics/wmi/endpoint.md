---
title: Endpoint
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452927"
---
# <a name="endpoint"></a><span data-ttu-id="5bcab-102">Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bcab-102">Endpoint</span></span>
<span data-ttu-id="5bcab-103">Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bcab-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bcab-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5bcab-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5bcab-105">Methods</span></span>  
 <span data-ttu-id="5bcab-106">La classe Endpoint definisce il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="5bcab-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="5bcab-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="5bcab-107">Method</span></span>|<span data-ttu-id="5bcab-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bcab-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bcab-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="5bcab-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="5bcab-110">Recupera il nome dell'istanza del contatore delle prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5bcab-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="5bcab-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5bcab-111">Properties</span></span>  
 <span data-ttu-id="5bcab-112">La classe Endpoint ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bcab-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="5bcab-113">Address</span><span class="sxs-lookup"><span data-stu-id="5bcab-113">Address</span></span>  
 <span data-ttu-id="5bcab-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-114">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-116">URI che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="5bcab-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="5bcab-117">AddressHeaders</span></span>  
 <span data-ttu-id="5bcab-118">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="5bcab-118">Data type: string array</span></span>  
  
 <span data-ttu-id="5bcab-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-120">Raccolta di intestazioni di indirizzo associato a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="5bcab-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="5bcab-121">AddressIdentity</span></span>  
 <span data-ttu-id="5bcab-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-122">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-124">Identità dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="5bcab-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="5bcab-125">AppDomainId</span></span>  
 <span data-ttu-id="5bcab-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="5bcab-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="5bcab-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-128">ID del dominio applicazione che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="5bcab-129">Comportamenti</span><span class="sxs-lookup"><span data-stu-id="5bcab-129">Behaviors</span></span>  
 <span data-ttu-id="5bcab-130">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="5bcab-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="5bcab-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-132">Raccolta dei comportamenti implementati da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="5bcab-133">Binding</span><span class="sxs-lookup"><span data-stu-id="5bcab-133">Binding</span></span>  
 <span data-ttu-id="5bcab-134">Tipo di dati: associazione</span><span class="sxs-lookup"><span data-stu-id="5bcab-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="5bcab-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-136">Associazione usata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="5bcab-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="5bcab-137">ContractName</span></span>  
 <span data-ttu-id="5bcab-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-138">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-140">Stringa che specifica il contratto che viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="5bcab-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="5bcab-141">CounterInstanceName</span></span>  
 <span data-ttu-id="5bcab-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-142">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-144">Nome dell'istanza del contatore delle prestazioni dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="5bcab-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="5bcab-145">ListenUri</span></span>  
 <span data-ttu-id="5bcab-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-146">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-148">URI sul quale resta in attesa l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="5bcab-149">Nome</span><span class="sxs-lookup"><span data-stu-id="5bcab-149">Name</span></span>  
 <span data-ttu-id="5bcab-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="5bcab-150">Data type: string</span></span>  
  
 <span data-ttu-id="5bcab-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-152">Nome univoco di questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="5bcab-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="5bcab-153">ProcessId</span></span>  
 <span data-ttu-id="5bcab-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="5bcab-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="5bcab-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-156">ID del processo che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="5bcab-157">ref</span><span class="sxs-lookup"><span data-stu-id="5bcab-157">ref</span></span>  
 <span data-ttu-id="5bcab-158">Tipo di dati: contratto</span><span class="sxs-lookup"><span data-stu-id="5bcab-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="5bcab-159">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5bcab-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bcab-160">Contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bcab-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcab-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bcab-161">Requirements</span></span>  
  
|<span data-ttu-id="5bcab-162">MOF</span><span class="sxs-lookup"><span data-stu-id="5bcab-162">MOF</span></span>|<span data-ttu-id="5bcab-163">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5bcab-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5bcab-164">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="5bcab-164">Namespace</span></span>|<span data-ttu-id="5bcab-165">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5bcab-165">Defined in root\ServiceModel</span></span>|
