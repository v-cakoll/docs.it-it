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
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202378"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="f247f-102">Metodo IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="f247f-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="f247f-103">Ottiene un puntatore al successivo [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) contenuto nell'oggetto [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="f247f-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f247f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f247f-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f247f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f247f-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="f247f-106">[out] L'oggetto restituito `IInstallReferenceItem` puntatore.</span><span class="sxs-lookup"><span data-stu-id="f247f-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f247f-107">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="f247f-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="f247f-108">deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f247f-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f247f-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="f247f-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="f247f-110">deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="f247f-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f247f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f247f-111">Requirements</span></span>  
 <span data-ttu-id="f247f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f247f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f247f-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f247f-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="f247f-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f247f-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f247f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f247f-115">See also</span></span>

- [<span data-ttu-id="f247f-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="f247f-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="f247f-117">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="f247f-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
