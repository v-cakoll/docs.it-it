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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159887"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="cae04-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="cae04-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="cae04-103">Elimina un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae04-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="cae04-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae04-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae04-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cae04-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cae04-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cae04-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="cae04-107">[in] Il `ICeeFileGen` oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="cae04-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cae04-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cae04-108">Return Value</span></span>  
 <span data-ttu-id="cae04-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="cae04-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cae04-110">Note</span><span class="sxs-lookup"><span data-stu-id="cae04-110">Remarks</span></span>  
 `DestroyICeeFileGen` <span data-ttu-id="cae04-111">Elimina definitivamente il `ICeeFileGen` oggetto creato tramite il [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="cae04-111">destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae04-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cae04-112">Requirements</span></span>  
 <span data-ttu-id="cae04-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cae04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae04-114">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="cae04-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="cae04-115">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="cae04-115">**Library:** MSCorPE.dll</span></span>  
  
 **<span data-ttu-id="cae04-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cae04-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cae04-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cae04-117">See also</span></span>

- [<span data-ttu-id="cae04-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="cae04-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
