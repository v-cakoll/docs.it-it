---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975156"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="3c012-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3c012-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="3c012-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="3c012-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c012-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c012-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3c012-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3c012-105">Methods</span></span>  
 <span data-ttu-id="3c012-106">La classe OperationBehaviorAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3c012-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3c012-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3c012-107">Properties</span></span>  
 <span data-ttu-id="3c012-108">La classe OperationBehaviorAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c012-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="3c012-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="3c012-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="3c012-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3c012-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="3c012-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3c012-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c012-112">Stato della funzionalità di eliminazione automatica per i parametri.</span><span class="sxs-lookup"><span data-stu-id="3c012-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="3c012-113">Rappresentazione</span><span class="sxs-lookup"><span data-stu-id="3c012-113">Impersonation</span></span>  
 <span data-ttu-id="3c012-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3c012-114">Data type: string</span></span>  
  
 <span data-ttu-id="3c012-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3c012-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c012-116">Indica il livello di rappresentazione del chiamante supportato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="3c012-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="3c012-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="3c012-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="3c012-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3c012-118">Data type: string</span></span>  
  
 <span data-ttu-id="3c012-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3c012-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c012-120">Indica quando riciclare l'oggetto nel corso della chiamata a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="3c012-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="3c012-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="3c012-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="3c012-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3c012-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3c012-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3c012-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c012-124">Indica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="3c012-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="3c012-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="3c012-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="3c012-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3c012-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="3c012-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3c012-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3c012-128">Indica se l'operazione richiede una transazione.</span><span class="sxs-lookup"><span data-stu-id="3c012-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c012-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c012-129">Requirements</span></span>  
  
|<span data-ttu-id="3c012-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3c012-130">MOF</span></span>|<span data-ttu-id="3c012-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3c012-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3c012-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3c012-132">Namespace</span></span>|<span data-ttu-id="3c012-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3c012-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c012-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c012-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
