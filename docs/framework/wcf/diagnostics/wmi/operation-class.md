---
title: Classe Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973200"
---
# <a name="operation-class"></a><span data-ttu-id="59e53-102">Classe Operation</span><span class="sxs-lookup"><span data-stu-id="59e53-102">Operation class</span></span>
<span data-ttu-id="59e53-103">Operazione</span><span class="sxs-lookup"><span data-stu-id="59e53-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59e53-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="59e53-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="59e53-105">Methods</span></span>  
 <span data-ttu-id="59e53-106">La classe Operation non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="59e53-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="59e53-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="59e53-107">Properties</span></span>  
 <span data-ttu-id="59e53-108">La classe Operation ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="59e53-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="59e53-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="59e53-109">Action</span></span>  
 <span data-ttu-id="59e53-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="59e53-110">Data type: string</span></span>  
  
 <span data-ttu-id="59e53-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-112">Azione WS-Addressing del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="59e53-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="59e53-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="59e53-113">AsyncPattern</span></span>  
 <span data-ttu-id="59e53-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="59e53-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="59e53-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-116">Indica che un'operazione è implementata in modo asincrono usando una `Begin`[apertura/chiusura parentesi quadre] e `End`coppia di metodi [parentesi quadre di apertura e chiusura] in un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="59e53-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="59e53-117">comportamenti</span><span class="sxs-lookup"><span data-stu-id="59e53-117">Behaviors</span></span>  
 <span data-ttu-id="59e53-118">Tipo di dati: Matrice di Behavior</span><span class="sxs-lookup"><span data-stu-id="59e53-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="59e53-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-120">Comportamenti associati all'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="59e53-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="59e53-121">IsCallback</span></span>  
 <span data-ttu-id="59e53-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="59e53-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="59e53-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-124">Restituisce True quando l'operazione è un'operazione di callback.</span><span class="sxs-lookup"><span data-stu-id="59e53-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="59e53-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="59e53-125">IsInitiating</span></span>  
 <span data-ttu-id="59e53-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="59e53-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="59e53-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-128">Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.</span><span class="sxs-lookup"><span data-stu-id="59e53-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="59e53-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="59e53-129">IsOneWay</span></span>  
 <span data-ttu-id="59e53-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="59e53-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="59e53-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-132">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="59e53-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="59e53-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="59e53-133">IsTerminating</span></span>  
 <span data-ttu-id="59e53-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="59e53-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="59e53-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-136">Indica se un'operazione restituisce un messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="59e53-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="59e53-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="59e53-137">MethodSignature</span></span>  
 <span data-ttu-id="59e53-138">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="59e53-138">Data type: string</span></span>  
  
 <span data-ttu-id="59e53-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-140">Firma del metodo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="59e53-141">Nome</span><span class="sxs-lookup"><span data-stu-id="59e53-141">Name</span></span>  
 <span data-ttu-id="59e53-142">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="59e53-142">Data type: string</span></span>  
  
 <span data-ttu-id="59e53-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-144">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="59e53-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="59e53-145">ParameterTypes</span></span>  
 <span data-ttu-id="59e53-146">Tipo di dati: matrice di stringhe</span><span class="sxs-lookup"><span data-stu-id="59e53-146">Data type: string array</span></span>  
  
 <span data-ttu-id="59e53-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-148">Tipi dei parametri dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="59e53-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="59e53-149">ReplyAction</span></span>  
 <span data-ttu-id="59e53-150">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="59e53-150">Data type: string</span></span>  
  
 <span data-ttu-id="59e53-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-152">Valore dell'azione SOAP del messaggio di risposta dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="59e53-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="59e53-153">ReturnType</span></span>  
 <span data-ttu-id="59e53-154">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="59e53-154">Data type: string</span></span>  
  
 <span data-ttu-id="59e53-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="59e53-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59e53-156">Tipo restituito dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="59e53-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e53-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59e53-157">Requirements</span></span>  
  
|<span data-ttu-id="59e53-158">MOF</span><span class="sxs-lookup"><span data-stu-id="59e53-158">MOF</span></span>|<span data-ttu-id="59e53-159">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="59e53-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="59e53-160">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="59e53-160">Namespace</span></span>|<span data-ttu-id="59e53-161">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59e53-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59e53-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59e53-162">See also</span></span>

- <xref:System.ServiceModel.Description.OperationDescription>
