---
title: Funzione CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bbd25909e70826f8cd29076c1eb62a4da6779cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435401"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="282dc-102">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="282dc-102">CoInitializeEE Function</span></span>
<span data-ttu-id="282dc-103">Assicura che il motore di esecuzione di common language runtime viene caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="282dc-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="282dc-104">Questa funzione è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="282dc-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="282dc-105">Utilizzare il [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="282dc-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282dc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="282dc-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="282dc-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="282dc-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="282dc-108">[in] Uno del [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="282dc-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="282dc-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="282dc-109">Return Value</span></span>  
 <span data-ttu-id="282dc-110">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="282dc-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="282dc-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="282dc-111">Return code</span></span>|<span data-ttu-id="282dc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="282dc-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="282dc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="282dc-113">S_OK</span></span>|<span data-ttu-id="282dc-114">Il motore di esecuzione è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="282dc-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="282dc-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="282dc-115">S_FALSE</span></span>|<span data-ttu-id="282dc-116">Il motore di esecuzione è già caricato.</span><span class="sxs-lookup"><span data-stu-id="282dc-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="282dc-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="282dc-117">E_FAIL</span></span>|<span data-ttu-id="282dc-118">Impossibile caricare il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="282dc-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="282dc-119">Note</span><span class="sxs-lookup"><span data-stu-id="282dc-119">Remarks</span></span>  
 <span data-ttu-id="282dc-120">Se non è stato caricato in precedenza, questo metodo carica il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="282dc-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="282dc-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="282dc-121">Requirements</span></span>  
 <span data-ttu-id="282dc-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="282dc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282dc-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="282dc-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="282dc-124">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="282dc-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="282dc-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282dc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282dc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="282dc-126">See Also</span></span>  
 [<span data-ttu-id="282dc-127">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="282dc-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
