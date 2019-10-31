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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131685"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="26248-102">Metodo IInstallReferenceItem::GetReference</span><span class="sxs-lookup"><span data-stu-id="26248-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="26248-103">Ottiene un puntatore alla struttura [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) rappresentata da questo oggetto [IInstallReferenceItem](iinstallreferenceitem-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="26248-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26248-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26248-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26248-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26248-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="26248-106">out Puntatore `FUSION_INSTALL_REFERENCE` restituito.</span><span class="sxs-lookup"><span data-stu-id="26248-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="26248-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="26248-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="26248-108">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="26248-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="26248-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="26248-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="26248-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="26248-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26248-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26248-111">Requirements</span></span>  
 <span data-ttu-id="26248-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26248-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26248-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="26248-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="26248-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26248-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26248-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26248-115">See also</span></span>

- [<span data-ttu-id="26248-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="26248-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="26248-117">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="26248-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
