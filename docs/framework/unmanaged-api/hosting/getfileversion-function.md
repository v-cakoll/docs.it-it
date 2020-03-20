---
title: Funzione GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178174"
---
# <a name="getfileversion-function"></a><span data-ttu-id="1be25-102">Funzione GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="1be25-102">GetFileVersion Function</span></span>
<span data-ttu-id="1be25-103">Ottiene le informazioni sulla versione di Common Language Runtime (CLR) del file specificato, utilizzando il buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="1be25-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="1be25-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1be25-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be25-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1be25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1be25-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1be25-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="1be25-107">[in] Percorso del file da esaminare.</span><span class="sxs-lookup"><span data-stu-id="1be25-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1be25-108">[in, out] Buffer allocato per le informazioni sulla versione restituite.</span><span class="sxs-lookup"><span data-stu-id="1be25-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="1be25-109">[in] La dimensione, in caratteri `szBuffer`larghi, di .</span><span class="sxs-lookup"><span data-stu-id="1be25-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="1be25-110">[fuori] Dimensione, in byte, dell'oggetto restituito. `szBuffer`</span><span class="sxs-lookup"><span data-stu-id="1be25-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be25-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1be25-111">Requirements</span></span>  
 <span data-ttu-id="1be25-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1be25-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be25-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1be25-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1be25-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be25-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be25-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1be25-115">See also</span></span>

- [<span data-ttu-id="1be25-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="1be25-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
