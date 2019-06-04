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
ms.openlocfilehash: daf674c0340998c0fd518e0f1af721bbe9ff653c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490476"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="3ca31-102">Funzione DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="3ca31-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="3ca31-103">Elimina un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ca31-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="3ca31-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3ca31-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca31-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ca31-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca31-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ca31-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="3ca31-107">[in] Il `ICeeFileGen` oggetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3ca31-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ca31-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ca31-108">Return Value</span></span>  
 <span data-ttu-id="3ca31-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="3ca31-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca31-110">Note</span><span class="sxs-lookup"><span data-stu-id="3ca31-110">Remarks</span></span>  
 <span data-ttu-id="3ca31-111">`DestroyICeeFileGen` Elimina definitivamente il `ICeeFileGen` oggetto creato tramite il [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="3ca31-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca31-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ca31-112">Requirements</span></span>  
 <span data-ttu-id="3ca31-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca31-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca31-114">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="3ca31-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="3ca31-115">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="3ca31-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="3ca31-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca31-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca31-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca31-117">See also</span></span>

- [<span data-ttu-id="3ca31-118">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="3ca31-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
