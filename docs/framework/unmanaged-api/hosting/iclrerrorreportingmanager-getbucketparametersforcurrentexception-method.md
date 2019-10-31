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
ms.openlocfilehash: b24f8ed4f5e2c6e0022f5599f2ab8c44a30a561a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129271"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="d2122-102">Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="d2122-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="d2122-103">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="d2122-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="d2122-104">Un *bucket* è una raccolta di dati di errore correlati allo stesso difetto del codice.</span><span class="sxs-lookup"><span data-stu-id="d2122-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="d2122-105">*Watson* si riferisce a un set di tecnologie per la raccolta e l'analisi dei dati associati a un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d2122-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2122-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2122-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2122-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2122-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="d2122-108">out Puntatore a una struttura [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) che contiene i dati di errore per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d2122-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2122-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2122-109">Requirements</span></span>  
 <span data-ttu-id="d2122-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2122-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2122-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d2122-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2122-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d2122-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2122-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2122-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2122-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2122-114">See also</span></span>

- [<span data-ttu-id="d2122-115">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="d2122-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
