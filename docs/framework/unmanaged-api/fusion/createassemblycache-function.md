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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c855d6f85c3cbfa6d81a1fbce3ef5b83abb3f583
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795414"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="b3254-102">Funzione CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="b3254-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="b3254-103">Ottiene un puntatore a una nuova istanza di [IAssemblyCache](iassemblycache-interface.md) che rappresenta l'global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="b3254-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3254-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3254-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3254-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3254-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="b3254-106">out Puntatore restituito `IAssemblyCache` .</span><span class="sxs-lookup"><span data-stu-id="b3254-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="b3254-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="b3254-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b3254-108">`dwReserved`deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b3254-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3254-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3254-109">Requirements</span></span>  
 <span data-ttu-id="b3254-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3254-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3254-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b3254-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b3254-112">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3254-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3254-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3254-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3254-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3254-114">See also</span></span>

- [<span data-ttu-id="b3254-115">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="b3254-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="b3254-116">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="b3254-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="b3254-117">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="b3254-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
