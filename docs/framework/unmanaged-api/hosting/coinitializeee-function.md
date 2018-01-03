---
title: Funzione CoInitializeEE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeEE
helpviewer_keywords: CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca564830411a9df0d47cc9765958286bbd40f96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="coinitializeee-function"></a><span data-ttu-id="8fb5d-102">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="8fb5d-102">CoInitializeEE Function</span></span>
<span data-ttu-id="8fb5d-103">Assicura che il motore di esecuzione di common language runtime viene caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="8fb5d-104">Questa funzione è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fb5d-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="8fb5d-105">Utilizzare il [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb5d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fb5d-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fb5d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fb5d-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="8fb5d-108">[in] Uno del [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fb5d-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8fb5d-109">Return Value</span></span>  
 <span data-ttu-id="8fb5d-110">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="8fb5d-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="8fb5d-111">Return code</span></span>|<span data-ttu-id="8fb5d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8fb5d-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8fb5d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fb5d-113">S_OK</span></span>|<span data-ttu-id="8fb5d-114">Il motore di esecuzione è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="8fb5d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8fb5d-115">S_FALSE</span></span>|<span data-ttu-id="8fb5d-116">Il motore di esecuzione è già caricato.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="8fb5d-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8fb5d-117">E_FAIL</span></span>|<span data-ttu-id="8fb5d-118">Impossibile caricare il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb5d-119">Note</span><span class="sxs-lookup"><span data-stu-id="8fb5d-119">Remarks</span></span>  
 <span data-ttu-id="8fb5d-120">Se non è stato caricato in precedenza, questo metodo carica il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fb5d-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fb5d-121">Requirements</span></span>  
 <span data-ttu-id="8fb5d-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fb5d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb5d-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8fb5d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fb5d-124">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fb5d-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fb5d-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fb5d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb5d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fb5d-126">See Also</span></span>  
 [<span data-ttu-id="8fb5d-127">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="8fb5d-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
