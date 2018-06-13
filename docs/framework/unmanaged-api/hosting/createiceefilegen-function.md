---
title: Funzione CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc98641085591feaaa5c97c7ee04885ef79d39f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429440"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="bed6e-102">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="bed6e-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="bed6e-103">Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="bed6e-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="bed6e-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bed6e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bed6e-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bed6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bed6e-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="bed6e-107">[out] Un puntatore all'indirizzo di un nuovo `ICeeFileGen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="bed6e-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bed6e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bed6e-108">Return Value</span></span>  
 <span data-ttu-id="bed6e-109">Questo metodo restituisce codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="bed6e-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bed6e-110">Note</span><span class="sxs-lookup"><span data-stu-id="bed6e-110">Remarks</span></span>  
 <span data-ttu-id="bed6e-111">Il `ICeeFileGen` oggetto viene utilizzato per creare common language runtime (CLR) i file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="bed6e-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="bed6e-112">Chiamare il [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) funzione eliminare definitivamente il `ICeeFileGen` al termine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bed6e-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed6e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bed6e-113">Requirements</span></span>  
 <span data-ttu-id="bed6e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bed6e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed6e-115">**Intestazione:** ICeeFileGen. H</span><span class="sxs-lookup"><span data-stu-id="bed6e-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="bed6e-116">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="bed6e-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="bed6e-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed6e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed6e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bed6e-118">See Also</span></span>  
 [<span data-ttu-id="bed6e-119">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="bed6e-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
