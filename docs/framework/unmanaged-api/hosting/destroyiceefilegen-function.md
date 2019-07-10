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
ms.openlocfilehash: ab4560774edce49341c86dd9446e38701db7fa62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769827"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="6c830-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="6c830-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="6c830-103">Elimina un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="6c830-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="6c830-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6c830-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c830-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c830-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c830-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c830-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="6c830-107">[in] Il `ICeeFileGen` oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="6c830-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c830-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c830-108">Return Value</span></span>  
 <span data-ttu-id="6c830-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="6c830-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c830-110">Note</span><span class="sxs-lookup"><span data-stu-id="6c830-110">Remarks</span></span>  
 <span data-ttu-id="6c830-111">`DestroyICeeFileGen` Elimina definitivamente il `ICeeFileGen` oggetto creato tramite il [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="6c830-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c830-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c830-112">Requirements</span></span>  
 <span data-ttu-id="6c830-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c830-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c830-114">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="6c830-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="6c830-115">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="6c830-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="6c830-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c830-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c830-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c830-117">See also</span></span>

- [<span data-ttu-id="6c830-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6c830-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
