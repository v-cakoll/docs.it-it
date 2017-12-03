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
ms.openlocfilehash: 492a3cb4b11706bfabc42976fb1adfad24a2279a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="operation-class"></a><span data-ttu-id="4fcfd-102">Classe Operation</span><span class="sxs-lookup"><span data-stu-id="4fcfd-102">Operation class</span></span>
<span data-ttu-id="4fcfd-103">Operazione</span><span class="sxs-lookup"><span data-stu-id="4fcfd-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fcfd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fcfd-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4fcfd-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4fcfd-105">Methods</span></span>  
 <span data-ttu-id="4fcfd-106">La classe Operation non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4fcfd-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4fcfd-107">Properties</span></span>  
 <span data-ttu-id="4fcfd-108">La classe Operation ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fcfd-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="4fcfd-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="4fcfd-109">Action</span></span>  
 <span data-ttu-id="4fcfd-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4fcfd-110">Data type: string</span></span>  
  
 <span data-ttu-id="4fcfd-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-112">Azione WS-Addressing del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="4fcfd-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="4fcfd-113">AsyncPattern</span></span>  
 <span data-ttu-id="4fcfd-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4fcfd-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fcfd-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-116">Indica che un'operazione è implementata in modo asincrono utilizzando un `Begin`[parentesi angolari aperte/chiuse] e `End`coppia di metodi [parentesi angolari aperte/chiuse] in un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="4fcfd-117">comportamenti</span><span class="sxs-lookup"><span data-stu-id="4fcfd-117">Behaviors</span></span>  
 <span data-ttu-id="4fcfd-118">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="4fcfd-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="4fcfd-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-120">Comportamenti associati all'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="4fcfd-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="4fcfd-121">IsCallback</span></span>  
 <span data-ttu-id="4fcfd-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4fcfd-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fcfd-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-124">Restituisce True quando l'operazione è un'operazione di callback.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="4fcfd-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="4fcfd-125">IsInitiating</span></span>  
 <span data-ttu-id="4fcfd-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4fcfd-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fcfd-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-128">Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="4fcfd-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="4fcfd-129">IsOneWay</span></span>  
 <span data-ttu-id="4fcfd-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4fcfd-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fcfd-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-132">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="4fcfd-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="4fcfd-133">IsTerminating</span></span>  
 <span data-ttu-id="4fcfd-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4fcfd-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fcfd-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-136">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="4fcfd-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="4fcfd-137">MethodSignature</span></span>  
 <span data-ttu-id="4fcfd-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4fcfd-138">Data type: string</span></span>  
  
 <span data-ttu-id="4fcfd-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-140">Firma del metodo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4fcfd-141">Nome</span><span class="sxs-lookup"><span data-stu-id="4fcfd-141">Name</span></span>  
 <span data-ttu-id="4fcfd-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4fcfd-142">Data type: string</span></span>  
  
 <span data-ttu-id="4fcfd-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-144">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="4fcfd-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="4fcfd-145">ParameterTypes</span></span>  
 <span data-ttu-id="4fcfd-146">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="4fcfd-146">Data type: string array</span></span>  
  
 <span data-ttu-id="4fcfd-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-148">Tipi dei parametri dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="4fcfd-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="4fcfd-149">ReplyAction</span></span>  
 <span data-ttu-id="4fcfd-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4fcfd-150">Data type: string</span></span>  
  
 <span data-ttu-id="4fcfd-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-152">Valore dell'azione SOAP del messaggio di risposta dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="4fcfd-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="4fcfd-153">ReturnType</span></span>  
 <span data-ttu-id="4fcfd-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4fcfd-154">Data type: string</span></span>  
  
 <span data-ttu-id="4fcfd-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="4fcfd-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fcfd-156">Tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fcfd-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fcfd-157">Requirements</span></span>  
  
|<span data-ttu-id="4fcfd-158">MOF</span><span class="sxs-lookup"><span data-stu-id="4fcfd-158">MOF</span></span>|<span data-ttu-id="4fcfd-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4fcfd-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4fcfd-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4fcfd-160">Namespace</span></span>|<span data-ttu-id="4fcfd-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4fcfd-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fcfd-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fcfd-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
