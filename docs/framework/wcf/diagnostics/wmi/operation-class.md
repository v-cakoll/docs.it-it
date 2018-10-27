---
title: Classe Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 16de8b25594896349ea546d3def52dd256fe5c70
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180939"
---
# <a name="operation-class"></a><span data-ttu-id="c4216-102">Classe Operation</span><span class="sxs-lookup"><span data-stu-id="c4216-102">Operation class</span></span>
<span data-ttu-id="c4216-103">Operazione</span><span class="sxs-lookup"><span data-stu-id="c4216-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4216-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4216-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="c4216-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c4216-105">Methods</span></span>  
 <span data-ttu-id="c4216-106">La classe Operation non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="c4216-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c4216-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c4216-107">Properties</span></span>  
 <span data-ttu-id="c4216-108">La classe Operation ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4216-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="c4216-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="c4216-109">Action</span></span>  
 <span data-ttu-id="c4216-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4216-110">Data type: string</span></span>  
  
 <span data-ttu-id="c4216-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-112">Azione WS-Addressing del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="c4216-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="c4216-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="c4216-113">AsyncPattern</span></span>  
 <span data-ttu-id="c4216-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4216-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4216-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-116">Indica che un'operazione è implementata in modo asincrono usando una `Begin`[apertura/chiusura parentesi quadre] e `End`coppia di metodi [parentesi quadre di apertura e chiusura] in un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="c4216-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c4216-117">comportamenti</span><span class="sxs-lookup"><span data-stu-id="c4216-117">Behaviors</span></span>  
 <span data-ttu-id="c4216-118">Tipo di dati: matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="c4216-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c4216-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-120">Comportamenti associati all'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="c4216-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="c4216-121">IsCallback</span></span>  
 <span data-ttu-id="c4216-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4216-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4216-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-124">Restituisce True quando l'operazione è un'operazione di callback.</span><span class="sxs-lookup"><span data-stu-id="c4216-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="c4216-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="c4216-125">IsInitiating</span></span>  
 <span data-ttu-id="c4216-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4216-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4216-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-128">Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.</span><span class="sxs-lookup"><span data-stu-id="c4216-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="c4216-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="c4216-129">IsOneWay</span></span>  
 <span data-ttu-id="c4216-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4216-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4216-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-132">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="c4216-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="c4216-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="c4216-133">IsTerminating</span></span>  
 <span data-ttu-id="c4216-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="c4216-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="c4216-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-136">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="c4216-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="c4216-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="c4216-137">MethodSignature</span></span>  
 <span data-ttu-id="c4216-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4216-138">Data type: string</span></span>  
  
 <span data-ttu-id="c4216-139">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-140">Firma del metodo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c4216-141">nome</span><span class="sxs-lookup"><span data-stu-id="c4216-141">Name</span></span>  
 <span data-ttu-id="c4216-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4216-142">Data type: string</span></span>  
  
 <span data-ttu-id="c4216-143">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-144">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="c4216-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="c4216-145">ParameterTypes</span></span>  
 <span data-ttu-id="c4216-146">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="c4216-146">Data type: string array</span></span>  
  
 <span data-ttu-id="c4216-147">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-148">Tipi dei parametri dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="c4216-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="c4216-149">ReplyAction</span></span>  
 <span data-ttu-id="c4216-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4216-150">Data type: string</span></span>  
  
 <span data-ttu-id="c4216-151">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-152">Valore dell'azione SOAP del messaggio di risposta dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="c4216-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="c4216-153">ReturnType</span></span>  
 <span data-ttu-id="c4216-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="c4216-154">Data type: string</span></span>  
  
 <span data-ttu-id="c4216-155">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4216-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4216-156">Tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4216-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4216-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4216-157">Requirements</span></span>  
  
|<span data-ttu-id="c4216-158">MOF</span><span class="sxs-lookup"><span data-stu-id="c4216-158">MOF</span></span>|<span data-ttu-id="c4216-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c4216-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c4216-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c4216-160">Namespace</span></span>|<span data-ttu-id="c4216-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c4216-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4216-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4216-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
