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
ms.openlocfilehash: 969d74933e908674225684a2e77d5c4804b86122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615644"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="aa22e-102">Metodo ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="aa22e-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="aa22e-103">Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="aa22e-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="aa22e-104">Un *bucket* è una raccolta di dati di errore correlati allo stesso difetto del codice.</span><span class="sxs-lookup"><span data-stu-id="aa22e-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="aa22e-105">*Watson* si riferisce a un set di tecnologie per la raccolta e l'analisi dei dati associati a un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa22e-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa22e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa22e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa22e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa22e-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="aa22e-108">out Puntatore a una struttura [BucketParameters](bucketparameters-structure.md) che contiene i dati di errore per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa22e-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa22e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa22e-109">Requirements</span></span>  
 <span data-ttu-id="aa22e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa22e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa22e-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aa22e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa22e-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa22e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa22e-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa22e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa22e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa22e-114">See also</span></span>

- [<span data-ttu-id="aa22e-115">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="aa22e-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
