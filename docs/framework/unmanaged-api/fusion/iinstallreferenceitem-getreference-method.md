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
ms.openlocfilehash: a6c64b98f3b5ab0445b076b0d3bacfaa398e26f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429768"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="18125-102">Metodo IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="18125-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="18125-103">Ottiene un puntatore per il [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) struttura rappresentato da questo [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="18125-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18125-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18125-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18125-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18125-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="18125-106">[out] L'oggetto restituito `FUSION_INSTALL_REFERENCE` puntatore.</span><span class="sxs-lookup"><span data-stu-id="18125-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="18125-107">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="18125-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="18125-108">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="18125-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="18125-109">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="18125-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="18125-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="18125-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18125-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18125-111">Requirements</span></span>  
 <span data-ttu-id="18125-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18125-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18125-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="18125-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="18125-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18125-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18125-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18125-115">See Also</span></span>  
 [<span data-ttu-id="18125-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="18125-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="18125-117">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="18125-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
