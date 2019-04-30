---
title: Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cb2a8d2a4e089d16b6c2129c165a9d8b6828f3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969813"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="c8722-102">Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="c8722-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="c8722-103">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="c8722-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="c8722-104">Oggetto *bucket* è una raccolta di dati di errore che sono correlati il difetto del codice stesso.</span><span class="sxs-lookup"><span data-stu-id="c8722-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="c8722-105">*Watson* fa riferimento a un set di tecnologie per la raccolta e analisi dei dati che sono associati a un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c8722-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8722-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8722-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8722-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8722-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="c8722-108">[out] Un puntatore a un [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) struttura che contiene i dati di errore per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c8722-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8722-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8722-109">Requirements</span></span>  
 <span data-ttu-id="c8722-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8722-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8722-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8722-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8722-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c8722-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8722-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8722-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8722-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8722-114">See also</span></span>

- [<span data-ttu-id="c8722-115">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="c8722-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
