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
ms.openlocfilehash: 20dbd0c86f012b6f29b752c4ad9195ce453f78b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="contract"></a><span data-ttu-id="0868d-102">Contratto</span><span class="sxs-lookup"><span data-stu-id="0868d-102">Contract</span></span>
<span data-ttu-id="0868d-103">Contratto</span><span class="sxs-lookup"><span data-stu-id="0868d-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0868d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0868d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0868d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0868d-105">Methods</span></span>  
 <span data-ttu-id="0868d-106">La classe Contract non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="0868d-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0868d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0868d-107">Properties</span></span>  
 <span data-ttu-id="0868d-108">La classe Contract ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0868d-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="0868d-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="0868d-109">AppDomainId</span></span>  
 <span data-ttu-id="0868d-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="0868d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="0868d-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-112">ID del dominio applicazione che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="0868d-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="0868d-113">Comportamenti</span><span class="sxs-lookup"><span data-stu-id="0868d-113">Behaviors</span></span>  
 <span data-ttu-id="0868d-114">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="0868d-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="0868d-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-116">Comportamenti associati al contratto.</span><span class="sxs-lookup"><span data-stu-id="0868d-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="0868d-117">Nome</span><span class="sxs-lookup"><span data-stu-id="0868d-117">Name</span></span>  
 <span data-ttu-id="0868d-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0868d-118">Data type: string</span></span>  
  
 <span data-ttu-id="0868d-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-120">Nome del contratto in WSDL.</span><span class="sxs-lookup"><span data-stu-id="0868d-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="0868d-121">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0868d-121">Namespace</span></span>  
 <span data-ttu-id="0868d-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0868d-122">Data type: string</span></span>  
  
 <span data-ttu-id="0868d-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-124">Spazio dei nomi dell'elemento `portType` in WSDL.</span><span class="sxs-lookup"><span data-stu-id="0868d-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="0868d-125">Operazioni</span><span class="sxs-lookup"><span data-stu-id="0868d-125">Operations</span></span>  
 <span data-ttu-id="0868d-126">Tipo di dati: matrice di Operation</span><span class="sxs-lookup"><span data-stu-id="0868d-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="0868d-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-128">Operazioni di questo contratto.</span><span class="sxs-lookup"><span data-stu-id="0868d-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="0868d-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="0868d-129">ProcessId</span></span>  
 <span data-ttu-id="0868d-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="0868d-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="0868d-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-132">ID del processo che ospita il contratto.</span><span class="sxs-lookup"><span data-stu-id="0868d-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0868d-133">ref</span><span class="sxs-lookup"><span data-stu-id="0868d-133">ref</span></span>  
 <span data-ttu-id="0868d-134">Tipo di dati: contratto</span><span class="sxs-lookup"><span data-stu-id="0868d-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="0868d-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-136">Tipo di callback se il contratto è duplex.</span><span class="sxs-lookup"><span data-stu-id="0868d-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="0868d-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="0868d-137">SessionMode</span></span>  
 <span data-ttu-id="0868d-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0868d-138">Data type: string</span></span>  
  
 <span data-ttu-id="0868d-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-140">Indica se il contratto richiede che l'associazione di questo contratto utilizzi le sessioni del canale.</span><span class="sxs-lookup"><span data-stu-id="0868d-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="0868d-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="0868d-141">Type</span></span>  
 <span data-ttu-id="0868d-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="0868d-142">Data type: string</span></span>  
  
 <span data-ttu-id="0868d-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="0868d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0868d-144">Tipo del contratto.</span><span class="sxs-lookup"><span data-stu-id="0868d-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0868d-145">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0868d-145">Requirements</span></span>  
  
|<span data-ttu-id="0868d-146">MOF</span><span class="sxs-lookup"><span data-stu-id="0868d-146">MOF</span></span>|<span data-ttu-id="0868d-147">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0868d-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0868d-148">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0868d-148">Namespace</span></span>|<span data-ttu-id="0868d-149">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0868d-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0868d-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0868d-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
