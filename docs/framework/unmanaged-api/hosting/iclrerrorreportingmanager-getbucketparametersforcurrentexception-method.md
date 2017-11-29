---
title: Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80bf3e9b1cee9f19534f985dccf4508467dbe26e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="909ce-102">Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="909ce-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="909ce-103">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="909ce-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="909ce-104">Oggetto *bucket* è una raccolta di dati di errore correlati allo stesso difetto del codice.</span><span class="sxs-lookup"><span data-stu-id="909ce-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="909ce-105">*Watson* fa riferimento a un set di tecnologie per la raccolta e analisi dei dati che sono associati a un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="909ce-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="909ce-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="909ce-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="909ce-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="909ce-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="909ce-108">[out] Un puntatore a un [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) struttura che contiene dati di errore per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="909ce-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="909ce-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="909ce-109">Requirements</span></span>  
 <span data-ttu-id="909ce-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="909ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="909ce-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="909ce-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="909ce-112">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="909ce-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="909ce-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="909ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909ce-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="909ce-114">See Also</span></span>  
 [<span data-ttu-id="909ce-115">ICLRErrorReportingManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="909ce-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
