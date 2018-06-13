---
title: Funzione NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0436991512713c05e60a3c10d6fbdaa17bb378c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429827"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="12904-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="12904-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="12904-103">Elimina la download cache common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="12904-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12904-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12904-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="12904-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="12904-105">Return Value</span></span>  
 <span data-ttu-id="12904-106">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H.</span><span class="sxs-lookup"><span data-stu-id="12904-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12904-107">Note</span><span class="sxs-lookup"><span data-stu-id="12904-107">Remarks</span></span>  
 <span data-ttu-id="12904-108">La download cache CLR è l'area in cui sono archiviati gli assembly con nome sicuro che vengono scaricati da un URL per un eventuale riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="12904-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12904-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12904-109">Requirements</span></span>  
 <span data-ttu-id="12904-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12904-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12904-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="12904-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="12904-112">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="12904-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="12904-113">Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="12904-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="12904-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12904-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12904-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12904-115">See Also</span></span>  
 [<span data-ttu-id="12904-116">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="12904-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="12904-117">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="12904-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="12904-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="12904-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
