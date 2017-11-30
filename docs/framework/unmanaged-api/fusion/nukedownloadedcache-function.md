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
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="8eaaf-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="8eaaf-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="8eaaf-103">Elimina la download cache common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8eaaf-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eaaf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8eaaf-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8eaaf-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8eaaf-105">Return Value</span></span>  
 <span data-ttu-id="8eaaf-106">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H.</span><span class="sxs-lookup"><span data-stu-id="8eaaf-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eaaf-107">Note</span><span class="sxs-lookup"><span data-stu-id="8eaaf-107">Remarks</span></span>  
 <span data-ttu-id="8eaaf-108">La download cache CLR è l'area in cui sono archiviati gli assembly con nome sicuro che vengono scaricati da un URL per un eventuale riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="8eaaf-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eaaf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8eaaf-109">Requirements</span></span>  
 <span data-ttu-id="8eaaf-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eaaf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eaaf-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8eaaf-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8eaaf-112">**Libreria:** Fusion e Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="8eaaf-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="8eaaf-113">Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8eaaf-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="8eaaf-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eaaf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaaf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eaaf-115">See Also</span></span>  
 [<span data-ttu-id="8eaaf-116">CreateHistoryReader (funzione)</span><span class="sxs-lookup"><span data-stu-id="8eaaf-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="8eaaf-117">GetHistoryFileDirectory (funzione)</span><span class="sxs-lookup"><span data-stu-id="8eaaf-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="8eaaf-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="8eaaf-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
