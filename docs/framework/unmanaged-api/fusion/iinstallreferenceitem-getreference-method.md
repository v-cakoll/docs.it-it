---
title: Metodo IInstallReferenceItem::GetReference
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85c3fb601cd013eff889e794e71512533f1b12ec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484680"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="795fa-102">Metodo IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="795fa-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="795fa-103">Ottiene un puntatore per il [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) rappresentato da questa struttura [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="795fa-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="795fa-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="795fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="795fa-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="795fa-106">[out] L'oggetto restituito `FUSION_INSTALL_REFERENCE` puntatore.</span><span class="sxs-lookup"><span data-stu-id="795fa-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="795fa-107">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="795fa-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="795fa-108">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="795fa-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="795fa-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="795fa-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="795fa-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="795fa-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="795fa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="795fa-111">Requirements</span></span>  
 <span data-ttu-id="795fa-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795fa-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="795fa-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="795fa-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="795fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795fa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="795fa-115">See also</span></span>
- [<span data-ttu-id="795fa-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="795fa-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="795fa-117">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="795fa-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
