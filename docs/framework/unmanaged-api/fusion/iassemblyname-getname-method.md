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
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134342"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="7b0e7-102">Metodo IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="7b0e7-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="7b0e7-103">Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7b0e7-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b0e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b0e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b0e7-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="7b0e7-106">[in, out] Dimensioni del `pwzName` in caratteri wide, incluso il carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="7b0e7-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="7b0e7-107">out Buffer che consente di memorizzare il nome dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="7b0e7-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b0e7-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b0e7-108">Requirements</span></span>  
 <span data-ttu-id="7b0e7-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b0e7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b0e7-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7b0e7-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7b0e7-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b0e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0e7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b0e7-112">See also</span></span>

- [<span data-ttu-id="7b0e7-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7b0e7-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
