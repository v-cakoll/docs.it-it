---
title: Metodo ICorPublishProcess::GetDisplayName
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2d3624d130c005f9ed9109863b052e3272797ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496819"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="97a9b-102">Metodo ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="97a9b-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="97a9b-103">Ottiene il percorso completo del file eseguibile per il processo a cui fa riferimento [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="97a9b-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97a9b-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97a9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97a9b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="97a9b-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="97a9b-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="97a9b-107">[out] Il numero di caratteri "wide", restituito nel `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="97a9b-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="97a9b-108">[out] Una matrice per archiviare il nome, incluso il percorso completo, del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="97a9b-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="97a9b-109">Il nome è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="97a9b-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a9b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97a9b-110">Requirements</span></span>  
 <span data-ttu-id="97a9b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a9b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a9b-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="97a9b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="97a9b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97a9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97a9b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a9b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a9b-115">See also</span></span>
- [<span data-ttu-id="97a9b-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="97a9b-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
