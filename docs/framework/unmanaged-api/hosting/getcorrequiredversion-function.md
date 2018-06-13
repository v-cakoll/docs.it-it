---
title: Funzione GetCORRequiredVersion
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 637ff0fca74dc123a3f7a47dcc3fdeded8d884ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430047"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="118fc-102">Funzione GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="118fc-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="118fc-103">Ottiene il numero di versione necessarie di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="118fc-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="118fc-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="118fc-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118fc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="118fc-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="118fc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="118fc-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="118fc-107">[out] Un buffer contenente una stringa che specifica il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="118fc-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="118fc-108">[in] Le dimensioni in byte, del buffer.</span><span class="sxs-lookup"><span data-stu-id="118fc-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="118fc-109">[out] Il numero di byte restituiti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="118fc-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="118fc-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="118fc-110">Requirements</span></span>  
 <span data-ttu-id="118fc-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="118fc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="118fc-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="118fc-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="118fc-113">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="118fc-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="118fc-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="118fc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118fc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="118fc-115">See Also</span></span>  
 [<span data-ttu-id="118fc-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="118fc-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
