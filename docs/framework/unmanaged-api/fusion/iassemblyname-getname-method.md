---
title: Metodo IAssemblyName::GetName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e471ee99af57ef980850c0a5d3e4f5f2973967ac
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796600"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="9bef4-102">Metodo IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="9bef4-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="9bef4-103">Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9bef4-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bef4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bef4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bef4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bef4-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="9bef4-106">[in, out] Dimensione in caratteri `pwzName` Wide, incluso il carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="9bef4-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="9bef4-107">out Buffer che consente di memorizzare il nome dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="9bef4-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bef4-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bef4-108">Requirements</span></span>  
 <span data-ttu-id="9bef4-109">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bef4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bef4-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9bef4-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9bef4-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bef4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bef4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bef4-112">See also</span></span>

- [<span data-ttu-id="9bef4-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9bef4-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
