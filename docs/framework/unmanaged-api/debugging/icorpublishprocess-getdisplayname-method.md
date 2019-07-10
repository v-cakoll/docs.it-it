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
ms.openlocfilehash: 354e1b0dad942534068d5fb07071ed4ac695fb49
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764892"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="6a808-102">Metodo ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="6a808-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="6a808-103">Ottiene il percorso completo del file eseguibile per il processo a cui fa riferimento [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6a808-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a808-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a808-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a808-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a808-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6a808-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="6a808-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6a808-107">[out] Il numero di caratteri "wide", restituito nel `szName` matrice.</span><span class="sxs-lookup"><span data-stu-id="6a808-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="6a808-108">[out] Una matrice per archiviare il nome, incluso il percorso completo, del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="6a808-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="6a808-109">Il nome è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="6a808-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a808-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a808-110">Requirements</span></span>  
 <span data-ttu-id="6a808-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a808-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a808-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6a808-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6a808-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a808-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a808-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a808-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a808-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a808-115">See also</span></span>

- [<span data-ttu-id="6a808-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="6a808-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
