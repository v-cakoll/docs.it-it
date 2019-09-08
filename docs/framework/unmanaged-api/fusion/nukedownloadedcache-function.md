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
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796300"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="96a2e-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="96a2e-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="96a2e-103">Elimina la Download Cache di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="96a2e-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96a2e-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="96a2e-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96a2e-105">Return Value</span></span>  
 <span data-ttu-id="96a2e-106">Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h.</span><span class="sxs-lookup"><span data-stu-id="96a2e-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96a2e-107">Note</span><span class="sxs-lookup"><span data-stu-id="96a2e-107">Remarks</span></span>  
 <span data-ttu-id="96a2e-108">Il Download Cache CLR è l'area in cui gli assembly con nome sicuro scaricati da un URL vengono archiviati per poter essere riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="96a2e-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96a2e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96a2e-109">Requirements</span></span>  
 <span data-ttu-id="96a2e-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96a2e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96a2e-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="96a2e-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="96a2e-112">**Libreria** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="96a2e-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="96a2e-113">Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96a2e-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="96a2e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96a2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a2e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96a2e-115">See also</span></span>

- [<span data-ttu-id="96a2e-116">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="96a2e-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="96a2e-117">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="96a2e-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="96a2e-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="96a2e-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
