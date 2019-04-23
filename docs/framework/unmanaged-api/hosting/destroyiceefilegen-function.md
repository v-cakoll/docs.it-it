---
title: Funzione DestroyICeeFileGen
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ff40e1c009b8e1e0509a4a3333d5a2a70bbfd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159887"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="da7c9-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="da7c9-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="da7c9-103">Elimina un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="da7c9-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="da7c9-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da7c9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da7c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da7c9-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da7c9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="da7c9-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="da7c9-107">[in] Il `ICeeFileGen` oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="da7c9-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da7c9-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da7c9-108">Return Value</span></span>  
 <span data-ttu-id="da7c9-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="da7c9-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da7c9-110">Note</span><span class="sxs-lookup"><span data-stu-id="da7c9-110">Remarks</span></span>  
 <span data-ttu-id="da7c9-111">`DestroyICeeFileGen` Elimina definitivamente il `ICeeFileGen` oggetto creato tramite il [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="da7c9-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da7c9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da7c9-112">Requirements</span></span>  
 <span data-ttu-id="da7c9-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da7c9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da7c9-114">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="da7c9-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="da7c9-115">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="da7c9-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="da7c9-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da7c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7c9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da7c9-117">See also</span></span>

- [<span data-ttu-id="da7c9-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="da7c9-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
