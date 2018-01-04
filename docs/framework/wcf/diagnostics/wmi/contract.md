---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04a5cb87b9ed61fd278ce0f2e05e5f1c954de5b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="contract"></a><span data-ttu-id="ad250-102">Contratto</span><span class="sxs-lookup"><span data-stu-id="ad250-102">Contract</span></span>
<span data-ttu-id="ad250-103">Contratto</span><span class="sxs-lookup"><span data-stu-id="ad250-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad250-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad250-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="ad250-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ad250-105">Methods</span></span>  
 <span data-ttu-id="ad250-106">La classe Contract non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ad250-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad250-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ad250-107">Properties</span></span>  
 <span data-ttu-id="ad250-108">La classe Contract ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad250-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="ad250-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="ad250-109">AppDomainId</span></span>  
 <span data-ttu-id="ad250-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="ad250-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="ad250-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-112">ID del dominio applicazione che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="ad250-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="ad250-113">Comportamenti</span><span class="sxs-lookup"><span data-stu-id="ad250-113">Behaviors</span></span>  
 <span data-ttu-id="ad250-114">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="ad250-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="ad250-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-116">Comportamenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="ad250-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="ad250-117">nome</span><span class="sxs-lookup"><span data-stu-id="ad250-117">Name</span></span>  
 <span data-ttu-id="ad250-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad250-118">Data type: string</span></span>  
  
 <span data-ttu-id="ad250-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-120">Nome del contratto in WSDL.</span><span class="sxs-lookup"><span data-stu-id="ad250-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="ad250-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ad250-121">Namespace</span></span>  
 <span data-ttu-id="ad250-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad250-122">Data type: string</span></span>  
  
 <span data-ttu-id="ad250-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-124">Spazio dei nomi dell'elemento `portType` in WSDL.</span><span class="sxs-lookup"><span data-stu-id="ad250-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="ad250-125">Operazioni</span><span class="sxs-lookup"><span data-stu-id="ad250-125">Operations</span></span>  
 <span data-ttu-id="ad250-126">Tipo di dati: matrice di Operation</span><span class="sxs-lookup"><span data-stu-id="ad250-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="ad250-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-128">Operazioni di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="ad250-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="ad250-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="ad250-129">ProcessId</span></span>  
 <span data-ttu-id="ad250-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="ad250-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="ad250-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-132">ID del processo che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="ad250-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ad250-133">ref</span><span class="sxs-lookup"><span data-stu-id="ad250-133">ref</span></span>  
 <span data-ttu-id="ad250-134">Tipo di dati: contratto</span><span class="sxs-lookup"><span data-stu-id="ad250-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="ad250-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-136">Tipo di callback se il contratto è duplex.</span><span class="sxs-lookup"><span data-stu-id="ad250-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="ad250-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="ad250-137">SessionMode</span></span>  
 <span data-ttu-id="ad250-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad250-138">Data type: string</span></span>  
  
 <span data-ttu-id="ad250-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-140">Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.</span><span class="sxs-lookup"><span data-stu-id="ad250-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="ad250-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad250-141">Type</span></span>  
 <span data-ttu-id="ad250-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ad250-142">Data type: string</span></span>  
  
 <span data-ttu-id="ad250-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ad250-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad250-144">Tipo del contratto.</span><span class="sxs-lookup"><span data-stu-id="ad250-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad250-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad250-145">Requirements</span></span>  
  
|<span data-ttu-id="ad250-146">MOF</span><span class="sxs-lookup"><span data-stu-id="ad250-146">MOF</span></span>|<span data-ttu-id="ad250-147">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ad250-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad250-148">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ad250-148">Namespace</span></span>|<span data-ttu-id="ad250-149">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad250-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad250-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad250-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
