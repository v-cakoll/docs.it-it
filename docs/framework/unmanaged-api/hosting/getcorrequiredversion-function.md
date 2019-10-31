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
ms.openlocfilehash: 661eb758e1651901bb56810640a68f0de0b4e851
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136474"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="0820a-102">Funzione GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="0820a-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="0820a-103">Ottiene il numero di versione Common Language Runtime (CLR) obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0820a-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="0820a-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0820a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0820a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0820a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0820a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0820a-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="0820a-107">out Buffer contenente una stringa che specifica il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="0820a-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0820a-108">in Dimensione, in byte, del buffer.</span><span class="sxs-lookup"><span data-stu-id="0820a-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0820a-109">out Numero di byte restituiti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0820a-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0820a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0820a-110">Requirements</span></span>  
 <span data-ttu-id="0820a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0820a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0820a-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0820a-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0820a-113">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0820a-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0820a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0820a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0820a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0820a-115">See also</span></span>

- [<span data-ttu-id="0820a-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="0820a-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
