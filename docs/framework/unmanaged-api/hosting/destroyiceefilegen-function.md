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
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136507"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="5f0ad-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="5f0ad-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="5f0ad-103">Elimina definitivamente un oggetto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="5f0ad-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="5f0ad-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5f0ad-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f0ad-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f0ad-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f0ad-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f0ad-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="5f0ad-107">in Oggetto `ICeeFileGen` da eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="5f0ad-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f0ad-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f0ad-108">Return Value</span></span>  
 <span data-ttu-id="5f0ad-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="5f0ad-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f0ad-110">Note</span><span class="sxs-lookup"><span data-stu-id="5f0ad-110">Remarks</span></span>  
 <span data-ttu-id="5f0ad-111">`DestroyICeeFileGen` Elimina l'oggetto `ICeeFileGen` creato dalla funzione [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5f0ad-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f0ad-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f0ad-112">Requirements</span></span>  
 <span data-ttu-id="5f0ad-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f0ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f0ad-114">**Intestazione:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="5f0ad-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="5f0ad-115">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="5f0ad-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="5f0ad-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f0ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0ad-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f0ad-117">See also</span></span>

- [<span data-ttu-id="5f0ad-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="5f0ad-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
