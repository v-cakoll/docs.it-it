---
title: Metodo IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b756cdcbbc852280e88fef2d1a2bf5f0125cbd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429211"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="93c38-102">Metodo IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="93c38-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="93c38-103">Ottiene un puntatore al successivo [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) contenuto nell'oggetto [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="93c38-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c38-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93c38-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93c38-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93c38-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="93c38-106">[out] L'oggetto restituito `IInstallReferenceItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="93c38-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="93c38-107">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="93c38-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="93c38-108">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="93c38-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="93c38-109">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="93c38-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="93c38-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="93c38-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c38-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93c38-111">Requirements</span></span>  
 <span data-ttu-id="93c38-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93c38-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93c38-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="93c38-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="93c38-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c38-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c38-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93c38-115">See Also</span></span>  
 [<span data-ttu-id="93c38-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="93c38-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="93c38-117">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="93c38-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
