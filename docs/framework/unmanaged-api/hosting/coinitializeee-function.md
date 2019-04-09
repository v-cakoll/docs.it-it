---
title: Funzione CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
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
ms.openlocfilehash: 18f1a4ede1a362860df1271835600e7b867eac00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127764"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="1729f-102">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="1729f-102">CoInitializeEE Function</span></span>
<span data-ttu-id="1729f-103">Garantisce che il motore di esecuzione di common language runtime è caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="1729f-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="1729f-104">Questa funzione è deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1729f-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="1729f-105">Usare la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="1729f-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1729f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1729f-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1729f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1729f-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="1729f-108">[in] Uno dei [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1729f-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1729f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1729f-109">Return Value</span></span>  
 <span data-ttu-id="1729f-110">Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. h e i valori nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1729f-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="1729f-111">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="1729f-111">Return code</span></span>|<span data-ttu-id="1729f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1729f-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1729f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1729f-113">S_OK</span></span>|<span data-ttu-id="1729f-114">Il motore di esecuzione è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1729f-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="1729f-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1729f-115">S_FALSE</span></span>|<span data-ttu-id="1729f-116">Il motore di esecuzione è già caricato.</span><span class="sxs-lookup"><span data-stu-id="1729f-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="1729f-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1729f-117">E_FAIL</span></span>|<span data-ttu-id="1729f-118">Non è stato possibile caricare il motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1729f-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1729f-119">Note</span><span class="sxs-lookup"><span data-stu-id="1729f-119">Remarks</span></span>  
 <span data-ttu-id="1729f-120">Questo metodo carica il motore di esecuzione se non è stato caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1729f-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1729f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1729f-121">Requirements</span></span>  
 <span data-ttu-id="1729f-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1729f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1729f-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1729f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1729f-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1729f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1729f-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1729f-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1729f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1729f-126">See also</span></span>

- [<span data-ttu-id="1729f-127">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="1729f-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
