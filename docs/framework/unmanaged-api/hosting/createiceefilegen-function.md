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
ms.openlocfilehash: 566f73335861a8eb769b21a254e0e93b51a78d02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756390"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="325e4-102">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="325e4-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="325e4-103">Crea un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="325e4-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="325e4-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="325e4-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325e4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="325e4-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325e4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="325e4-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="325e4-107">[out] Un puntatore all'indirizzo di un nuovo `ICeeFileGen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="325e4-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="325e4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="325e4-108">Return Value</span></span>  
 <span data-ttu-id="325e4-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="325e4-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325e4-110">Note</span><span class="sxs-lookup"><span data-stu-id="325e4-110">Remarks</span></span>  
 <span data-ttu-id="325e4-111">Il `ICeeFileGen` oggetto viene usato per creare common language runtime (CLR) i file eseguibili portabili (PE).</span><span class="sxs-lookup"><span data-stu-id="325e4-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="325e4-112">Chiamare il [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) funzione eliminare definitivamente il `ICeeFileGen` al termine dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="325e4-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325e4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="325e4-113">Requirements</span></span>  
 <span data-ttu-id="325e4-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="325e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="325e4-115">**Intestazione:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="325e4-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="325e4-116">**Libreria:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="325e4-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="325e4-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="325e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325e4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="325e4-118">See also</span></span>

- [<span data-ttu-id="325e4-119">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="325e4-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
