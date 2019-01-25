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
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720093"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="b8cf4-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="b8cf4-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="b8cf4-103">Elimina la download cache common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b8cf4-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8cf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8cf4-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b8cf4-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8cf4-105">Return Value</span></span>  
 <span data-ttu-id="b8cf4-106">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H.</span><span class="sxs-lookup"><span data-stu-id="b8cf4-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8cf4-107">Note</span><span class="sxs-lookup"><span data-stu-id="b8cf4-107">Remarks</span></span>  
 <span data-ttu-id="b8cf4-108">La download cache CLR è l'area in cui sono archiviati gli assembly con nome sicuro che vengono scaricati da un URL per un eventuale riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="b8cf4-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8cf4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8cf4-109">Requirements</span></span>  
 <span data-ttu-id="b8cf4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8cf4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8cf4-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b8cf4-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b8cf4-112">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="b8cf4-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b8cf4-113">Usare Fusion. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8cf4-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b8cf4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8cf4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8cf4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8cf4-115">See also</span></span>
- [<span data-ttu-id="b8cf4-116">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="b8cf4-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="b8cf4-117">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="b8cf4-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="b8cf4-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="b8cf4-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
