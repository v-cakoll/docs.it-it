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
ms.openlocfilehash: 8e108dd925432b8ec193863de4cb085dad50cdd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429073"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="a4d51-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="a4d51-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="a4d51-103">Elimina definitivamente un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4d51-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="a4d51-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d51-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d51-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4d51-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4d51-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4d51-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="a4d51-107">[in] Il `ICeeFileGen` oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="a4d51-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4d51-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a4d51-108">Return Value</span></span>  
 <span data-ttu-id="a4d51-109">Questo metodo restituisce codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="a4d51-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4d51-110">Note</span><span class="sxs-lookup"><span data-stu-id="a4d51-110">Remarks</span></span>  
 <span data-ttu-id="a4d51-111">`DestroyICeeFileGen` Elimina definitivamente il `ICeeFileGen` l'oggetto creato con il [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="a4d51-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d51-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4d51-112">Requirements</span></span>  
 <span data-ttu-id="a4d51-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d51-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d51-114">**Intestazione:** ICeeFileGen. H</span><span class="sxs-lookup"><span data-stu-id="a4d51-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="a4d51-115">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="a4d51-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="a4d51-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d51-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d51-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4d51-117">See Also</span></span>  
 [<span data-ttu-id="a4d51-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="a4d51-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
