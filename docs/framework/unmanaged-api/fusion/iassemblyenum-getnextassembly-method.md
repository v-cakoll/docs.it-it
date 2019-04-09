---
title: Metodo IAssemblyEnum::GetNextAssembly
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a77e468363b59e76e55aa24d97d064189ad297e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117748"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="a5e82-102">Metodo IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="a5e82-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="a5e82-103">Ottiene un puntatore al successivo [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contenute in questo [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="a5e82-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5e82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5e82-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5e82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5e82-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="a5e82-106">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="a5e82-106">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="a5e82-107">deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="a5e82-107">must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a5e82-108">[out] L'oggetto restituito `IAssemblyName` puntatore.</span><span class="sxs-lookup"><span data-stu-id="a5e82-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a5e82-109">[in] Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="a5e82-109">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="a5e82-110">deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a5e82-110">must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5e82-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5e82-111">Requirements</span></span>  
 <span data-ttu-id="a5e82-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5e82-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5e82-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a5e82-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="a5e82-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a5e82-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5e82-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5e82-115">See also</span></span>

- [<span data-ttu-id="a5e82-116">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a5e82-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="a5e82-117">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a5e82-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
