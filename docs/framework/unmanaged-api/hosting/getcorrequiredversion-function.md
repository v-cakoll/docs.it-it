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
ms.openlocfilehash: ddb9792c00d6b78b29b66bbc3ef59ee4ad8bd81d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490408"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="e1d59-102">Funzione GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e1d59-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="e1d59-103">Ottiene il numero di versione necessaria di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e1d59-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="e1d59-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e1d59-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d59-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1d59-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1d59-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1d59-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="e1d59-107">[out] Un buffer contenente una stringa che specifica il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="e1d59-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e1d59-108">[in] Le dimensioni, in byte, del buffer.</span><span class="sxs-lookup"><span data-stu-id="e1d59-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e1d59-109">[out] Il numero di byte restituiti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="e1d59-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d59-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1d59-110">Requirements</span></span>  
 <span data-ttu-id="e1d59-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1d59-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d59-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1d59-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1d59-113">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1d59-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1d59-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d59-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d59-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1d59-115">See also</span></span>

- [<span data-ttu-id="e1d59-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e1d59-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
