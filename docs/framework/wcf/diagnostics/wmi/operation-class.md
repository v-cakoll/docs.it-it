---
title: Classe Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963111"
---
# <a name="operation-class"></a><span data-ttu-id="30717-102">Classe Operation</span><span class="sxs-lookup"><span data-stu-id="30717-102">Operation class</span></span>
<span data-ttu-id="30717-103">Operazione</span><span class="sxs-lookup"><span data-stu-id="30717-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30717-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30717-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="30717-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="30717-105">Methods</span></span>  
 <span data-ttu-id="30717-106">La classe Operation non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="30717-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="30717-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="30717-107">Properties</span></span>  
 <span data-ttu-id="30717-108">La classe Operation ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="30717-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="30717-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="30717-109">Action</span></span>  
 <span data-ttu-id="30717-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30717-110">Data type: string</span></span>  
  
 <span data-ttu-id="30717-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-112">Azione WS-Addressing del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="30717-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="30717-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="30717-113">AsyncPattern</span></span>  
 <span data-ttu-id="30717-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30717-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="30717-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-116">Indica che un'operazione è implementata in modo asincrono usando una `Begin`[apertura/chiusura parentesi quadre] e `End`coppia di metodi [parentesi quadre di apertura e chiusura] in un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="30717-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="30717-117">comportamenti</span><span class="sxs-lookup"><span data-stu-id="30717-117">Behaviors</span></span>  
 <span data-ttu-id="30717-118">Tipo di dati: Matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="30717-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="30717-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-120">Comportamenti associati all'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="30717-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="30717-121">IsCallback</span></span>  
 <span data-ttu-id="30717-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30717-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="30717-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-124">Restituisce True quando l'operazione è un'operazione di callback.</span><span class="sxs-lookup"><span data-stu-id="30717-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="30717-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="30717-125">IsInitiating</span></span>  
 <span data-ttu-id="30717-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30717-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="30717-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-128">Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.</span><span class="sxs-lookup"><span data-stu-id="30717-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="30717-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="30717-129">IsOneWay</span></span>  
 <span data-ttu-id="30717-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30717-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="30717-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-132">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="30717-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="30717-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="30717-133">IsTerminating</span></span>  
 <span data-ttu-id="30717-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30717-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="30717-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-136">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="30717-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="30717-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="30717-137">MethodSignature</span></span>  
 <span data-ttu-id="30717-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30717-138">Data type: string</span></span>  
  
 <span data-ttu-id="30717-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-140">Firma del metodo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="30717-141">Nome</span><span class="sxs-lookup"><span data-stu-id="30717-141">Name</span></span>  
 <span data-ttu-id="30717-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30717-142">Data type: string</span></span>  
  
 <span data-ttu-id="30717-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-144">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="30717-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="30717-145">ParameterTypes</span></span>  
 <span data-ttu-id="30717-146">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="30717-146">Data type: string array</span></span>  
  
 <span data-ttu-id="30717-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-148">Tipi dei parametri dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="30717-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="30717-149">ReplyAction</span></span>  
 <span data-ttu-id="30717-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30717-150">Data type: string</span></span>  
  
 <span data-ttu-id="30717-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-152">Valore dell'azione SOAP del messaggio di risposta dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="30717-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="30717-153">ReturnType</span></span>  
 <span data-ttu-id="30717-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30717-154">Data type: string</span></span>  
  
 <span data-ttu-id="30717-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="30717-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30717-156">Tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="30717-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30717-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30717-157">Requirements</span></span>  
  
|<span data-ttu-id="30717-158">MOF</span><span class="sxs-lookup"><span data-stu-id="30717-158">MOF</span></span>|<span data-ttu-id="30717-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="30717-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="30717-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="30717-160">Namespace</span></span>|<span data-ttu-id="30717-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="30717-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30717-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30717-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
