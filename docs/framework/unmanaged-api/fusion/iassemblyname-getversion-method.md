---
title: Metodo IAssemblyName::GetVersion
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
ms.openlocfilehash: c0a43dc1640bdaa0ae104832eb4d1f8eb15b0392
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134337"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="aa680-102">Metodo IAssemblyName::GetVersion</span><span class="sxs-lookup"><span data-stu-id="aa680-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="aa680-103">Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="aa680-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa680-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa680-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa680-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa680-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="aa680-106">out Bit 32 alti della versione.</span><span class="sxs-lookup"><span data-stu-id="aa680-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="aa680-107">out Bit 32 bassi della versione.</span><span class="sxs-lookup"><span data-stu-id="aa680-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa680-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa680-108">Requirements</span></span>  
 <span data-ttu-id="aa680-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa680-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa680-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="aa680-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="aa680-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa680-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa680-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa680-112">See also</span></span>

- [<span data-ttu-id="aa680-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="aa680-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
