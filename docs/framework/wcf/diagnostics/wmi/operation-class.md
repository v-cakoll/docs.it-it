---
title: Classe Operation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54566bc452baa2e02cef7d8d13d29fcd5864c95c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="operation-class"></a><span data-ttu-id="dc62c-102">Classe Operation</span><span class="sxs-lookup"><span data-stu-id="dc62c-102">Operation class</span></span>
<span data-ttu-id="dc62c-103">Operazione</span><span class="sxs-lookup"><span data-stu-id="dc62c-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc62c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc62c-104">Syntax</span></span>  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dc62c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dc62c-105">Methods</span></span>  
 <span data-ttu-id="dc62c-106">La classe Operation non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="dc62c-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dc62c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dc62c-107">Properties</span></span>  
 <span data-ttu-id="dc62c-108">La classe Operation ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc62c-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="dc62c-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="dc62c-109">Action</span></span>  
 <span data-ttu-id="dc62c-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc62c-110">Data type: string</span></span>  
  
 <span data-ttu-id="dc62c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-112">Azione WS-Addressing del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="dc62c-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="dc62c-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="dc62c-113">AsyncPattern</span></span>  
 <span data-ttu-id="dc62c-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dc62c-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc62c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-116">Indica che un'operazione è implementata in modo asincrono utilizzando un `Begin`[parentesi angolari aperte/chiuse] e `End`coppia di metodi [parentesi angolari aperte/chiuse] in un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="dc62c-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="dc62c-117">comportamenti</span><span class="sxs-lookup"><span data-stu-id="dc62c-117">Behaviors</span></span>  
 <span data-ttu-id="dc62c-118">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="dc62c-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="dc62c-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-120">Comportamenti associati all'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="dc62c-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="dc62c-121">IsCallback</span></span>  
 <span data-ttu-id="dc62c-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dc62c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc62c-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-124">Restituisce True quando l'operazione è un'operazione di callback.</span><span class="sxs-lookup"><span data-stu-id="dc62c-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="dc62c-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="dc62c-125">IsInitiating</span></span>  
 <span data-ttu-id="dc62c-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dc62c-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc62c-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-128">Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.</span><span class="sxs-lookup"><span data-stu-id="dc62c-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="dc62c-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="dc62c-129">IsOneWay</span></span>  
 <span data-ttu-id="dc62c-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dc62c-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc62c-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-132">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="dc62c-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="dc62c-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="dc62c-133">IsTerminating</span></span>  
 <span data-ttu-id="dc62c-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dc62c-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="dc62c-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-136">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="dc62c-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="dc62c-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="dc62c-137">MethodSignature</span></span>  
 <span data-ttu-id="dc62c-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc62c-138">Data type: string</span></span>  
  
 <span data-ttu-id="dc62c-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-140">Firma del metodo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="dc62c-141">nome</span><span class="sxs-lookup"><span data-stu-id="dc62c-141">Name</span></span>  
 <span data-ttu-id="dc62c-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc62c-142">Data type: string</span></span>  
  
 <span data-ttu-id="dc62c-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-144">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="dc62c-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="dc62c-145">ParameterTypes</span></span>  
 <span data-ttu-id="dc62c-146">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="dc62c-146">Data type: string array</span></span>  
  
 <span data-ttu-id="dc62c-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-148">Tipi dei parametri dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="dc62c-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="dc62c-149">ReplyAction</span></span>  
 <span data-ttu-id="dc62c-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc62c-150">Data type: string</span></span>  
  
 <span data-ttu-id="dc62c-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-152">Valore dell'azione SOAP del messaggio di risposta dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="dc62c-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="dc62c-153">ReturnType</span></span>  
 <span data-ttu-id="dc62c-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dc62c-154">Data type: string</span></span>  
  
 <span data-ttu-id="dc62c-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dc62c-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc62c-156">Tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc62c-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc62c-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc62c-157">Requirements</span></span>  
  
|<span data-ttu-id="dc62c-158">MOF</span><span class="sxs-lookup"><span data-stu-id="dc62c-158">MOF</span></span>|<span data-ttu-id="dc62c-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dc62c-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dc62c-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="dc62c-160">Namespace</span></span>|<span data-ttu-id="dc62c-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc62c-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc62c-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc62c-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
