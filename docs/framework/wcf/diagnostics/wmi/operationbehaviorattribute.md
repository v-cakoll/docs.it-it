---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da0bc2ac9a4283ec9b23a1d4767f664de071ef47
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="ca0fc-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ca0fc-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="ca0fc-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ca0fc-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca0fc-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ca0fc-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca0fc-105">Methods</span></span>  
 <span data-ttu-id="ca0fc-106">La classe OperationBehaviorAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ca0fc-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ca0fc-107">Properties</span></span>  
 <span data-ttu-id="ca0fc-108">La classe OperationBehaviorAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca0fc-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="ca0fc-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="ca0fc-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="ca0fc-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ca0fc-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ca0fc-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ca0fc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca0fc-112">Stato della funzionalità di eliminazione automatica per i parametri.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="ca0fc-113">Rappresentazione</span><span class="sxs-lookup"><span data-stu-id="ca0fc-113">Impersonation</span></span>  
 <span data-ttu-id="ca0fc-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ca0fc-114">Data type: string</span></span>  
  
 <span data-ttu-id="ca0fc-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ca0fc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca0fc-116">Indica il livello di rappresentazione del chiamante supportato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="ca0fc-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="ca0fc-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="ca0fc-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ca0fc-118">Data type: string</span></span>  
  
 <span data-ttu-id="ca0fc-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ca0fc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca0fc-120">Indica quando riciclare l'oggetto nel corso della chiamata a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="ca0fc-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="ca0fc-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="ca0fc-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ca0fc-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ca0fc-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ca0fc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca0fc-124">Indica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="ca0fc-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="ca0fc-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="ca0fc-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ca0fc-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="ca0fc-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ca0fc-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca0fc-128">Indica se l'operazione richiede una transazione.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca0fc-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca0fc-129">Requirements</span></span>  
  
|<span data-ttu-id="ca0fc-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ca0fc-130">MOF</span></span>|<span data-ttu-id="ca0fc-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ca0fc-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ca0fc-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ca0fc-132">Namespace</span></span>|<span data-ttu-id="ca0fc-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ca0fc-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca0fc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca0fc-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
