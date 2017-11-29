---
title: Metodo IAssemblyName::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 612efc9d5334fd34cc61f2243914de59370c45a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="f782e-102">Metodo IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="f782e-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="f782e-103">Ottiene il nome semplice non crittografato dell'assembly a cui fa riferimento questo [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="f782e-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f782e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f782e-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f782e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f782e-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="f782e-106">[in, out] Le dimensioni di `pwzName` in caratteri wide, incluso il carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f782e-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="f782e-107">[out] Un buffer contenente il nome dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f782e-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f782e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f782e-108">Requirements</span></span>  
 <span data-ttu-id="f782e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f782e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f782e-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f782e-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f782e-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f782e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f782e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f782e-112">See Also</span></span>  
 [<span data-ttu-id="f782e-113">IAssemblyName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f782e-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
