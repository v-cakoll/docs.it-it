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
ms.openlocfilehash: 9395fcc6d896114c25770edbc17761323285099f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796403"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="ea976-102">Metodo IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="ea976-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="ea976-103">Ottiene un puntatore alla struttura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) rappresentata da questo oggetto [IInstallReferenceItem](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ea976-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea976-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea976-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea976-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea976-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="ea976-106">out Puntatore restituito `FUSION_INSTALL_REFERENCE` .</span><span class="sxs-lookup"><span data-stu-id="ea976-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ea976-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="ea976-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ea976-108">`dwFlags`deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="ea976-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ea976-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="ea976-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ea976-110">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="ea976-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea976-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea976-111">Requirements</span></span>  
 <span data-ttu-id="ea976-112">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea976-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea976-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ea976-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ea976-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea976-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea976-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea976-115">See also</span></span>

- [<span data-ttu-id="ea976-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ea976-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="ea976-117">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="ea976-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
