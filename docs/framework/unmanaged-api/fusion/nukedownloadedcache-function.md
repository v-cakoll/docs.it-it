---
title: Funzione NukeDownloadedCache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31d7ba7d5f4a9268ea1e04a4c9f09cd17ebfd5bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="41fa9-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="41fa9-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="41fa9-103">Elimina la download cache common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="41fa9-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fa9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41fa9-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="41fa9-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="41fa9-105">Return Value</span></span>  
 <span data-ttu-id="41fa9-106">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H.</span><span class="sxs-lookup"><span data-stu-id="41fa9-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41fa9-107">Note</span><span class="sxs-lookup"><span data-stu-id="41fa9-107">Remarks</span></span>  
 <span data-ttu-id="41fa9-108">La download cache CLR è l'area in cui sono archiviati gli assembly con nome sicuro che vengono scaricati da un URL per un eventuale riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="41fa9-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fa9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41fa9-109">Requirements</span></span>  
 <span data-ttu-id="41fa9-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41fa9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41fa9-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="41fa9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41fa9-112">**Libreria:** Fusion e Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="41fa9-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="41fa9-113">Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="41fa9-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="41fa9-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41fa9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fa9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41fa9-115">See Also</span></span>  
 [<span data-ttu-id="41fa9-116">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="41fa9-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="41fa9-117">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="41fa9-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="41fa9-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="41fa9-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
