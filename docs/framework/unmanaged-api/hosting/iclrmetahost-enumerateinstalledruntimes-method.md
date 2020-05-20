---
title: Metodo ICLRMetaHost::EnumerateInstalledRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: c99607bfe5fda01eb1abfd7771cb3907ddabeec5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703782"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="9f193-102">Metodo ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="9f193-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="9f193-103">Restituisce un'enumerazione che contiene un'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valida per ogni versione di Common Language Runtime (CLR) installata in un computer.</span><span class="sxs-lookup"><span data-stu-id="9f193-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f193-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f193-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f193-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f193-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="9f193-106">out Enumerazione delle interfacce [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrispondono a ogni versione di CLR installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="9f193-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f193-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f193-107">Return Value</span></span>  
 <span data-ttu-id="9f193-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9f193-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9f193-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f193-109">HRESULT</span></span>|<span data-ttu-id="9f193-110">Description</span><span class="sxs-lookup"><span data-stu-id="9f193-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f193-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f193-111">S_OK</span></span>|<span data-ttu-id="9f193-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9f193-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f193-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f193-113">E_POINTER</span></span>|<span data-ttu-id="9f193-114">`ppEnumerator` è null.</span><span class="sxs-lookup"><span data-stu-id="9f193-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f193-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f193-115">Requirements</span></span>  
 <span data-ttu-id="9f193-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f193-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f193-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9f193-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9f193-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f193-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f193-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f193-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f193-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f193-120">See also</span></span>

- [<span data-ttu-id="9f193-121">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="9f193-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="9f193-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="9f193-122">Hosting</span></span>](index.md)
