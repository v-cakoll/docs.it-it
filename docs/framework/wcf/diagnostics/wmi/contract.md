---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12e9cbf5232ebbad33ccc4fdca33233997d27357
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50044944"
---
# <a name="contract"></a><span data-ttu-id="62e66-102">Contratto</span><span class="sxs-lookup"><span data-stu-id="62e66-102">Contract</span></span>
<span data-ttu-id="62e66-103">Contratto</span><span class="sxs-lookup"><span data-stu-id="62e66-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62e66-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="62e66-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="62e66-105">Methods</span></span>  
 <span data-ttu-id="62e66-106">La classe Contract non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="62e66-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62e66-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="62e66-107">Properties</span></span>  
 <span data-ttu-id="62e66-108">La classe Contract ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="62e66-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="62e66-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="62e66-109">AppDomainId</span></span>  
 <span data-ttu-id="62e66-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="62e66-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="62e66-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-112">ID del dominio applicazione che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="62e66-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="62e66-113">Comportamenti</span><span class="sxs-lookup"><span data-stu-id="62e66-113">Behaviors</span></span>  
 <span data-ttu-id="62e66-114">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="62e66-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="62e66-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-116">Comportamenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="62e66-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="62e66-117">nome</span><span class="sxs-lookup"><span data-stu-id="62e66-117">Name</span></span>  
 <span data-ttu-id="62e66-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="62e66-118">Data type: string</span></span>  
  
 <span data-ttu-id="62e66-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-120">Nome del contratto in WSDL.</span><span class="sxs-lookup"><span data-stu-id="62e66-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="62e66-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="62e66-121">Namespace</span></span>  
 <span data-ttu-id="62e66-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="62e66-122">Data type: string</span></span>  
  
 <span data-ttu-id="62e66-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-124">Spazio dei nomi dell'elemento `portType` in WSDL.</span><span class="sxs-lookup"><span data-stu-id="62e66-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="62e66-125">Operazioni</span><span class="sxs-lookup"><span data-stu-id="62e66-125">Operations</span></span>  
 <span data-ttu-id="62e66-126">Tipo di dati: matrice di Operation</span><span class="sxs-lookup"><span data-stu-id="62e66-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="62e66-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-128">Operazioni di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="62e66-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="62e66-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="62e66-129">ProcessId</span></span>  
 <span data-ttu-id="62e66-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="62e66-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="62e66-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-132">ID del processo che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="62e66-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="62e66-133">ref</span><span class="sxs-lookup"><span data-stu-id="62e66-133">ref</span></span>  
 <span data-ttu-id="62e66-134">Tipo di dati: contratto</span><span class="sxs-lookup"><span data-stu-id="62e66-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="62e66-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-136">Tipo di callback se il contratto è duplex.</span><span class="sxs-lookup"><span data-stu-id="62e66-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="62e66-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="62e66-137">SessionMode</span></span>  
 <span data-ttu-id="62e66-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="62e66-138">Data type: string</span></span>  
  
 <span data-ttu-id="62e66-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-140">Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.</span><span class="sxs-lookup"><span data-stu-id="62e66-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="62e66-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="62e66-141">Type</span></span>  
 <span data-ttu-id="62e66-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="62e66-142">Data type: string</span></span>  
  
 <span data-ttu-id="62e66-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="62e66-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62e66-144">Tipo del contratto.</span><span class="sxs-lookup"><span data-stu-id="62e66-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e66-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62e66-145">Requirements</span></span>  
  
|<span data-ttu-id="62e66-146">MOF</span><span class="sxs-lookup"><span data-stu-id="62e66-146">MOF</span></span>|<span data-ttu-id="62e66-147">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62e66-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62e66-148">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="62e66-148">Namespace</span></span>|<span data-ttu-id="62e66-149">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="62e66-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62e66-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62e66-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
