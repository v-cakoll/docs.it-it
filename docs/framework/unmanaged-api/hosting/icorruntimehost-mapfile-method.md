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
ms.openlocfilehash: 45b88758c339cd77bc7e17e0c29969f8783555f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436624"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="583f9-102">Metodo ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="583f9-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="583f9-103">Il file specificato viene eseguito il mapping in memoria.</span><span class="sxs-lookup"><span data-stu-id="583f9-103">Maps the specified file into memory.</span></span> <span data-ttu-id="583f9-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="583f9-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="583f9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="583f9-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="583f9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="583f9-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="583f9-107">[in] Handle di file da mappare.</span><span class="sxs-lookup"><span data-stu-id="583f9-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="583f9-108">[out] L'indirizzo di memoria iniziale da cui iniziare il file di mapping.</span><span class="sxs-lookup"><span data-stu-id="583f9-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="583f9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="583f9-109">Requirements</span></span>  
 <span data-ttu-id="583f9-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="583f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="583f9-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="583f9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="583f9-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="583f9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="583f9-113">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="583f9-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583f9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="583f9-114">See Also</span></span>  
 [<span data-ttu-id="583f9-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="583f9-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
