---
title: Metodo ICorRuntimeHost::MapFile
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956de98fca1caec0ac1b94afc7251f9741246f94
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494779"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="ffb62-102">Metodo ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="ffb62-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="ffb62-103">Il file specificato viene eseguito il mapping in memoria.</span><span class="sxs-lookup"><span data-stu-id="ffb62-103">Maps the specified file into memory.</span></span> <span data-ttu-id="ffb62-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ffb62-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb62-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffb62-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffb62-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ffb62-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="ffb62-107">[in] L'handle del file da mappare.</span><span class="sxs-lookup"><span data-stu-id="ffb62-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="ffb62-108">[out] L'indirizzo di memoria iniziale da cui iniziare il file di mapping.</span><span class="sxs-lookup"><span data-stu-id="ffb62-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb62-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffb62-109">Requirements</span></span>  
 <span data-ttu-id="ffb62-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffb62-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffb62-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffb62-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffb62-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ffb62-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffb62-113">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ffb62-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb62-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffb62-114">See also</span></span>
- [<span data-ttu-id="ffb62-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ffb62-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
