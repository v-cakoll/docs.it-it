---
title: Endpoint
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963605"
---
# <a name="endpoint"></a><span data-ttu-id="9d605-102">Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d605-102">Endpoint</span></span>
<span data-ttu-id="9d605-103">Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d605-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d605-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d605-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9d605-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9d605-105">Methods</span></span>  
 <span data-ttu-id="9d605-106">La classe Endpoint definisce il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="9d605-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="9d605-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="9d605-107">Method</span></span>|<span data-ttu-id="9d605-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d605-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d605-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="9d605-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="9d605-110">Recupera il nome dell'istanza del contatore delle prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="9d605-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="9d605-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9d605-111">Properties</span></span>  
 <span data-ttu-id="9d605-112">La classe Endpoint ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d605-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="9d605-113">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="9d605-113">Address</span></span>  
 <span data-ttu-id="9d605-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-114">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-116">URI che contiene l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="9d605-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="9d605-117">AddressHeaders</span></span>  
 <span data-ttu-id="9d605-118">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="9d605-118">Data type: string array</span></span>  
  
 <span data-ttu-id="9d605-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-120">Raccolta di intestazioni di indirizzo associato a questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="9d605-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="9d605-121">AddressIdentity</span></span>  
 <span data-ttu-id="9d605-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-122">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-124">Identità dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="9d605-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="9d605-125">AppDomainId</span></span>  
 <span data-ttu-id="9d605-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="9d605-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d605-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-128">ID del dominio applicazione che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="9d605-129">comportamenti</span><span class="sxs-lookup"><span data-stu-id="9d605-129">Behaviors</span></span>  
 <span data-ttu-id="9d605-130">Tipo di dati: Matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="9d605-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="9d605-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-132">Raccolta dei comportamenti implementati da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="9d605-133">Binding</span><span class="sxs-lookup"><span data-stu-id="9d605-133">Binding</span></span>  
 <span data-ttu-id="9d605-134">Tipo di dati: Binding</span><span class="sxs-lookup"><span data-stu-id="9d605-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="9d605-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-136">Associazione usata da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="9d605-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="9d605-137">ContractName</span></span>  
 <span data-ttu-id="9d605-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-138">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-140">Stringa che specifica il contratto che viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="9d605-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="9d605-141">CounterInstanceName</span></span>  
 <span data-ttu-id="9d605-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-142">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-144">Nome dell'istanza del contatore delle prestazioni dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="9d605-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="9d605-145">ListenUri</span></span>  
 <span data-ttu-id="9d605-146">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-146">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-148">URI sul quale resta in attesa l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="9d605-149">Nome</span><span class="sxs-lookup"><span data-stu-id="9d605-149">Name</span></span>  
 <span data-ttu-id="9d605-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="9d605-150">Data type: string</span></span>  
  
 <span data-ttu-id="9d605-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-152">Nome univoco di questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="9d605-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="9d605-153">ProcessId</span></span>  
 <span data-ttu-id="9d605-154">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="9d605-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d605-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-156">ID del processo che ospita l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9d605-157">ref</span><span class="sxs-lookup"><span data-stu-id="9d605-157">ref</span></span>  
 <span data-ttu-id="9d605-158">Tipo di dati: Contratto</span><span class="sxs-lookup"><span data-stu-id="9d605-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="9d605-159">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="9d605-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d605-160">Contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9d605-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d605-161">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d605-161">Requirements</span></span>  
  
|<span data-ttu-id="9d605-162">MOF</span><span class="sxs-lookup"><span data-stu-id="9d605-162">MOF</span></span>|<span data-ttu-id="9d605-163">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9d605-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d605-164">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="9d605-164">Namespace</span></span>|<span data-ttu-id="9d605-165">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d605-165">Defined in root\ServiceModel</span></span>|
