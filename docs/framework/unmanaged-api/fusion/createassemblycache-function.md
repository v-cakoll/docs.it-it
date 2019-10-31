---
title: Funzione CreateAssemblyCache
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108871"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="ee278-102">Funzione CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="ee278-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="ee278-103">Ottiene un puntatore a una nuova istanza di [IAssemblyCache](iassemblycache-interface.md) che rappresenta l'global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="ee278-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee278-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee278-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee278-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee278-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="ee278-106">out Puntatore `IAssemblyCache` restituito.</span><span class="sxs-lookup"><span data-stu-id="ee278-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="ee278-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="ee278-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ee278-108">`dwReserved` deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="ee278-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee278-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee278-109">Requirements</span></span>  
 <span data-ttu-id="ee278-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee278-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee278-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ee278-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ee278-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee278-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee278-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee278-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee278-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee278-114">See also</span></span>

- [<span data-ttu-id="ee278-115">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="ee278-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="ee278-116">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="ee278-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="ee278-117">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="ee278-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
