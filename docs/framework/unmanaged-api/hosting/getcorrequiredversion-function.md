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
ms.openlocfilehash: 6b9fd62102056a8d5f859ac913f4786f04c1df7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617243"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="6f366-102">Funzione GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="6f366-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="6f366-103">Ottiene il numero di versione Common Language Runtime (CLR) obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6f366-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="6f366-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6f366-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f366-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f366-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f366-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f366-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="6f366-107">out Buffer contenente una stringa che specifica il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="6f366-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6f366-108">in Dimensione, in byte, del buffer.</span><span class="sxs-lookup"><span data-stu-id="6f366-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6f366-109">out Numero di byte restituiti nel buffer.</span><span class="sxs-lookup"><span data-stu-id="6f366-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f366-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f366-110">Requirements</span></span>  
 <span data-ttu-id="6f366-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f366-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f366-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6f366-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f366-113">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6f366-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f366-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f366-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f366-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f366-115">See also</span></span>

- [<span data-ttu-id="6f366-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6f366-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
