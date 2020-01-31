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
ms.openlocfilehash: 7f2e644340a2ec7fe807830422b927ce811ddcf9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790569"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="3f5bf-102">Metodo ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="3f5bf-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="3f5bf-103">Ottiene il percorso completo dell'eseguibile per il processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3f5bf-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f5bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f5bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f5bf-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3f5bf-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="3f5bf-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3f5bf-107">out Numero di caratteri wide restituiti nella matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="3f5bf-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="3f5bf-108">out Una matrice in cui archiviare il nome, incluso il percorso completo, del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="3f5bf-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="3f5bf-109">Il nome è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="3f5bf-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f5bf-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3f5bf-110">Requirements</span></span>  
 <span data-ttu-id="3f5bf-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f5bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f5bf-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3f5bf-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3f5bf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f5bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f5bf-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f5bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5bf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f5bf-115">See also</span></span>

- [<span data-ttu-id="3f5bf-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="3f5bf-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
