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
ms.openlocfilehash: 77e801b048709949c384f642fc0d0ecb5d7eb512
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178390"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="f0b7d-102">Metodo ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="f0b7d-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="f0b7d-103">Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f0b7d-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0b7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b7d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0b7d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f0b7d-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="f0b7d-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f0b7d-107">[fuori] Numero di caratteri di tipo `szName` "wide" restituiti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f0b7d-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="f0b7d-108">[fuori] Matrice in cui archiviare il nome, incluso il percorso completo, dell'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f0b7d-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="f0b7d-109">Il nome è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f0b7d-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b7d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0b7d-110">Requirements</span></span>  
 <span data-ttu-id="f0b7d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b7d-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f0b7d-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f0b7d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b7d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0b7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b7d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0b7d-115">See also</span></span>

- [<span data-ttu-id="f0b7d-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="f0b7d-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
