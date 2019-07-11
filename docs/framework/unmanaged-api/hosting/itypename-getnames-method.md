---
title: Metodo ITypeName::GetNames
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c8ca51a9b1875e28a6e4824da40090f17e38f07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780534"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="48553-102">Metodo ITypeName::GetNames</span><span class="sxs-lookup"><span data-stu-id="48553-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="48553-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="48553-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48553-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48553-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="48553-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48553-105">Requirements</span></span>  
 <span data-ttu-id="48553-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48553-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48553-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48553-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48553-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="48553-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48553-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48553-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48553-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48553-110">See also</span></span>

- [<span data-ttu-id="48553-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="48553-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
