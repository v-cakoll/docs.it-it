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
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757677"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="8e2fb-102">Metodo IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="8e2fb-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="8e2fb-103">Ottiene un puntatore per il [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) rappresentato da questa struttura [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="8e2fb-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e2fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e2fb-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e2fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e2fb-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="8e2fb-106">[out] L'oggetto restituito `FUSION_INSTALL_REFERENCE` puntatore.</span><span class="sxs-lookup"><span data-stu-id="8e2fb-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8e2fb-107">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="8e2fb-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8e2fb-108">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="8e2fb-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8e2fb-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="8e2fb-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8e2fb-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="8e2fb-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e2fb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e2fb-111">Requirements</span></span>  
 <span data-ttu-id="8e2fb-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e2fb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e2fb-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8e2fb-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8e2fb-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e2fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e2fb-115">See also</span></span>

- [<span data-ttu-id="8e2fb-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="8e2fb-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="8e2fb-117">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="8e2fb-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
