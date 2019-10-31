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
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134441"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="9e4e1-102">Metodo IAssemblyEnum::GetNextAssembly</span><span class="sxs-lookup"><span data-stu-id="9e4e1-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="9e4e1-103">Ottiene un puntatore al [IAssemblyName](iassemblyname-interface.md) successivo contenuto nell'oggetto [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9e4e1-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e4e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e4e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e4e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e4e1-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="9e4e1-106">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="9e4e1-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9e4e1-107">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="9e4e1-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="9e4e1-108">out Puntatore `IAssemblyName` restituito.</span><span class="sxs-lookup"><span data-stu-id="9e4e1-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9e4e1-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="9e4e1-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9e4e1-110">`dwFlags` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="9e4e1-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e4e1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e4e1-111">Requirements</span></span>  
 <span data-ttu-id="9e4e1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e4e1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e4e1-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9e4e1-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9e4e1-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e4e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e4e1-115">See also</span></span>

- [<span data-ttu-id="9e4e1-116">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9e4e1-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9e4e1-117">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="9e4e1-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
