---
title: Funzione GetAssemblyIdentityFromFile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyIdentityFromFile
helpviewer_keywords: GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f3374553df02193a6b726f37a53a929533e86cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="6014b-102">Funzione GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="6014b-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="6014b-103">Ottiene un puntatore a un `IUnknown` oggetto con l'oggetto specificato `IID` nell'assembly nel percorso del file specificato.</span><span class="sxs-lookup"><span data-stu-id="6014b-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6014b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6014b-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6014b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6014b-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="6014b-106">[in] Un percorso valido per l'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="6014b-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="6014b-107">[in] Il `IID` dell'interfaccia da restituire.</span><span class="sxs-lookup"><span data-stu-id="6014b-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="6014b-108">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="6014b-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6014b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6014b-109">Requirements</span></span>  
 <span data-ttu-id="6014b-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6014b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6014b-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6014b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6014b-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6014b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6014b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6014b-113">See Also</span></span>  
 <span data-ttu-id="6014b-114"><<!--zzxref:IUnknown --> `IUnknown`></span><span class="sxs-lookup"><span data-stu-id="6014b-114"><<!--zzxref:IUnknown --> `IUnknown`></span></span>  
 [<span data-ttu-id="6014b-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="6014b-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
