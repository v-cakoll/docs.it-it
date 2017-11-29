---
title: Metodo ICorRuntimeHost::MapFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="b41cb-102">Metodo ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="b41cb-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="b41cb-103">Il file specificato viene eseguito il mapping in memoria.</span><span class="sxs-lookup"><span data-stu-id="b41cb-103">Maps the specified file into memory.</span></span> <span data-ttu-id="b41cb-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b41cb-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41cb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b41cb-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b41cb-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b41cb-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="b41cb-107">[in] Handle di file da mappare.</span><span class="sxs-lookup"><span data-stu-id="b41cb-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="b41cb-108">[out] L'indirizzo di memoria iniziale da cui iniziare il file di mapping.</span><span class="sxs-lookup"><span data-stu-id="b41cb-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41cb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b41cb-109">Requirements</span></span>  
 <span data-ttu-id="b41cb-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b41cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b41cb-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b41cb-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b41cb-112">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b41cb-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b41cb-113">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b41cb-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41cb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b41cb-114">See Also</span></span>  
 [<span data-ttu-id="b41cb-115">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b41cb-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
