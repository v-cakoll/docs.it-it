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
ms.openlocfilehash: 20e2bff4257df64f761fd8fff880643d4e786748
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796452"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="d28fb-102">Metodo IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="d28fb-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="d28fb-103">Ottiene un puntatore al successivo oggetto [IInstallReferenceItem](iinstallreferenceitem-interface.md) contenuto nell'oggetto [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d28fb-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d28fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d28fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d28fb-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="d28fb-106">out Puntatore restituito `IInstallReferenceItem` .</span><span class="sxs-lookup"><span data-stu-id="d28fb-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d28fb-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="d28fb-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d28fb-108">`dwFlags`deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="d28fb-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="d28fb-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="d28fb-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="d28fb-110">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="d28fb-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d28fb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d28fb-111">Requirements</span></span>  
 <span data-ttu-id="d28fb-112">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d28fb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d28fb-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d28fb-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d28fb-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d28fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d28fb-115">See also</span></span>

- [<span data-ttu-id="d28fb-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="d28fb-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="d28fb-117">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="d28fb-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
