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
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131693"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="4b574-102">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="4b574-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="4b574-103">Elimina la Download Cache di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4b574-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b574-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b574-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4b574-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b574-105">Return Value</span></span>  
 <span data-ttu-id="4b574-106">Questo metodo restituisce i codici di errore COM standard, come definito in WinError. h.</span><span class="sxs-lookup"><span data-stu-id="4b574-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b574-107">Note</span><span class="sxs-lookup"><span data-stu-id="4b574-107">Remarks</span></span>  
 <span data-ttu-id="4b574-108">Il Download Cache CLR è l'area in cui gli assembly con nome sicuro scaricati da un URL vengono archiviati per poter essere riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="4b574-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b574-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b574-109">Requirements</span></span>  
 <span data-ttu-id="4b574-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b574-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b574-111">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4b574-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4b574-112">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="4b574-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="4b574-113">Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b574-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="4b574-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b574-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b574-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b574-115">See also</span></span>

- [<span data-ttu-id="4b574-116">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="4b574-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="4b574-117">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="4b574-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="4b574-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="4b574-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
