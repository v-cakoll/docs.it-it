---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963696"
---
# <a name="contract"></a><span data-ttu-id="3e416-102">Contratto</span><span class="sxs-lookup"><span data-stu-id="3e416-102">Contract</span></span>
<span data-ttu-id="3e416-103">Contratto</span><span class="sxs-lookup"><span data-stu-id="3e416-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e416-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e416-104">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e416-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e416-105">Methods</span></span>  
 <span data-ttu-id="3e416-106">La classe Contract non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3e416-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e416-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3e416-107">Properties</span></span>  
 <span data-ttu-id="3e416-108">La classe Contract ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e416-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="3e416-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="3e416-109">AppDomainId</span></span>  
 <span data-ttu-id="3e416-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3e416-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3e416-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-112">ID del dominio applicazione che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="3e416-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="3e416-113">comportamenti</span><span class="sxs-lookup"><span data-stu-id="3e416-113">Behaviors</span></span>  
 <span data-ttu-id="3e416-114">Tipo di dati: Matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="3e416-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="3e416-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-116">Comportamenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="3e416-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="3e416-117">Nome</span><span class="sxs-lookup"><span data-stu-id="3e416-117">Name</span></span>  
 <span data-ttu-id="3e416-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e416-118">Data type: string</span></span>  
  
 <span data-ttu-id="3e416-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-120">Nome del contratto in WSDL.</span><span class="sxs-lookup"><span data-stu-id="3e416-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="3e416-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3e416-121">Namespace</span></span>  
 <span data-ttu-id="3e416-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e416-122">Data type: string</span></span>  
  
 <span data-ttu-id="3e416-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-124">Spazio dei nomi dell'elemento `portType` in WSDL.</span><span class="sxs-lookup"><span data-stu-id="3e416-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="3e416-125">Operazioni</span><span class="sxs-lookup"><span data-stu-id="3e416-125">Operations</span></span>  
 <span data-ttu-id="3e416-126">Tipo di dati: Matrice di Operation</span><span class="sxs-lookup"><span data-stu-id="3e416-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="3e416-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-128">Operazioni di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="3e416-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="3e416-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="3e416-129">ProcessId</span></span>  
 <span data-ttu-id="3e416-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3e416-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="3e416-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-132">ID del processo che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="3e416-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="3e416-133">ref</span><span class="sxs-lookup"><span data-stu-id="3e416-133">ref</span></span>  
 <span data-ttu-id="3e416-134">Tipo di dati: Contratto</span><span class="sxs-lookup"><span data-stu-id="3e416-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="3e416-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-136">Tipo di callback se il contratto è duplex.</span><span class="sxs-lookup"><span data-stu-id="3e416-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="3e416-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="3e416-137">SessionMode</span></span>  
 <span data-ttu-id="3e416-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e416-138">Data type: string</span></span>  
  
 <span data-ttu-id="3e416-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-140">Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.</span><span class="sxs-lookup"><span data-stu-id="3e416-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="3e416-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e416-141">Type</span></span>  
 <span data-ttu-id="3e416-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e416-142">Data type: string</span></span>  
  
 <span data-ttu-id="3e416-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e416-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e416-144">Tipo del contratto.</span><span class="sxs-lookup"><span data-stu-id="3e416-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e416-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e416-145">Requirements</span></span>  
  
|<span data-ttu-id="3e416-146">MOF</span><span class="sxs-lookup"><span data-stu-id="3e416-146">MOF</span></span>|<span data-ttu-id="3e416-147">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3e416-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e416-148">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3e416-148">Namespace</span></span>|<span data-ttu-id="3e416-149">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3e416-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e416-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e416-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
