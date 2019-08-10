---
title: Contratto
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: e4a21e95a6f1f1860ed36c968d17bb8ac8465dce
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868440"
---
# <a name="contract"></a><span data-ttu-id="c62e5-102">Contratto</span><span class="sxs-lookup"><span data-stu-id="c62e5-102">Contract</span></span>
<span data-ttu-id="c62e5-103">Contratto</span><span class="sxs-lookup"><span data-stu-id="c62e5-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c62e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c62e5-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c62e5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c62e5-105">Methods</span></span>  
 <span data-ttu-id="c62e5-106">La classe Contract non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c62e5-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c62e5-107">Properties</span><span class="sxs-lookup"><span data-stu-id="c62e5-107">Properties</span></span>  
 <span data-ttu-id="c62e5-108">La classe Contract ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c62e5-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="c62e5-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="c62e5-109">AppDomainId</span></span>  
 <span data-ttu-id="c62e5-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c62e5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="c62e5-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-112">ID del dominio applicazione che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="c62e5-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c62e5-113">comportamenti</span><span class="sxs-lookup"><span data-stu-id="c62e5-113">Behaviors</span></span>  
 <span data-ttu-id="c62e5-114">Tipo di dati: Matrice di comportamenti</span><span class="sxs-lookup"><span data-stu-id="c62e5-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c62e5-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-116">Comportamenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="c62e5-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c62e5-117">NOME</span><span class="sxs-lookup"><span data-stu-id="c62e5-117">Name</span></span>  
 <span data-ttu-id="c62e5-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c62e5-118">Data type: string</span></span>  
  
 <span data-ttu-id="c62e5-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-120">Nome del contratto in WSDL.</span><span class="sxs-lookup"><span data-stu-id="c62e5-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c62e5-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c62e5-121">Namespace</span></span>  
 <span data-ttu-id="c62e5-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c62e5-122">Data type: string</span></span>  
  
 <span data-ttu-id="c62e5-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-124">Spazio dei nomi dell'elemento `portType` in WSDL.</span><span class="sxs-lookup"><span data-stu-id="c62e5-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="c62e5-125">Operazioni</span><span class="sxs-lookup"><span data-stu-id="c62e5-125">Operations</span></span>  
 <span data-ttu-id="c62e5-126">Tipo di dati: Matrice Operation</span><span class="sxs-lookup"><span data-stu-id="c62e5-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="c62e5-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-128">Operazioni di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="c62e5-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c62e5-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c62e5-129">ProcessId</span></span>  
 <span data-ttu-id="c62e5-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="c62e5-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="c62e5-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-132">ID del processo che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="c62e5-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c62e5-133">ref</span><span class="sxs-lookup"><span data-stu-id="c62e5-133">ref</span></span>  
 <span data-ttu-id="c62e5-134">Tipo di dati: Contratto</span><span class="sxs-lookup"><span data-stu-id="c62e5-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="c62e5-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-136">Tipo di callback se il contratto è duplex.</span><span class="sxs-lookup"><span data-stu-id="c62e5-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="c62e5-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="c62e5-137">SessionMode</span></span>  
 <span data-ttu-id="c62e5-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c62e5-138">Data type: string</span></span>  
  
 <span data-ttu-id="c62e5-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-140">Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.</span><span class="sxs-lookup"><span data-stu-id="c62e5-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="c62e5-141">Type</span><span class="sxs-lookup"><span data-stu-id="c62e5-141">Type</span></span>  
 <span data-ttu-id="c62e5-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c62e5-142">Data type: string</span></span>  
  
 <span data-ttu-id="c62e5-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="c62e5-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c62e5-144">Tipo del contratto.</span><span class="sxs-lookup"><span data-stu-id="c62e5-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c62e5-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c62e5-145">Requirements</span></span>  
  
|<span data-ttu-id="c62e5-146">MOF</span><span class="sxs-lookup"><span data-stu-id="c62e5-146">MOF</span></span>|<span data-ttu-id="c62e5-147">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c62e5-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c62e5-148">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c62e5-148">Namespace</span></span>|<span data-ttu-id="c62e5-149">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c62e5-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c62e5-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c62e5-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
