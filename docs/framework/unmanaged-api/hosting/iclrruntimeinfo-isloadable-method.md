---
title: Metodo ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 13b4e00cf002abca625dbdda010f7d8994360687
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762539"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="f118f-102">Metodo ICLRRuntimeInfo::IsLoadable</span><span class="sxs-lookup"><span data-stu-id="f118f-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="f118f-103">Indica se il runtime associato a questa interfaccia può essere caricato nel processo corrente, tenendo conto di altri runtime che potrebbero essere già stati caricati nel processo.</span><span class="sxs-lookup"><span data-stu-id="f118f-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f118f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f118f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f118f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f118f-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="f118f-106">[out] `true` Se il runtime può essere caricato nel processo corrente; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f118f-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f118f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f118f-107">Return Value</span></span>  
 <span data-ttu-id="f118f-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="f118f-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f118f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f118f-109">HRESULT</span></span>|<span data-ttu-id="f118f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f118f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f118f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f118f-111">S_OK</span></span>|<span data-ttu-id="f118f-112">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f118f-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="f118f-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f118f-113">E_POINTER</span></span>|<span data-ttu-id="f118f-114">`pbLoadable` è null.</span><span class="sxs-lookup"><span data-stu-id="f118f-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f118f-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f118f-115">Remarks</span></span>  
 <span data-ttu-id="f118f-116">Se un altro runtime è già caricato nel processo e il runtime associato a questa interfaccia può essere caricato per l'esecuzione side-by-side in-process, `pbLoadable` restituisce `true` .</span><span class="sxs-lookup"><span data-stu-id="f118f-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="f118f-117">Se i due runtime non possono essere eseguiti side-by-side in-process, `pbLoadable` restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="f118f-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="f118f-118">Ad esempio, il Common Language Runtime (CLR) versione 4 può essere eseguito side-by-side nello stesso processo con CLR versione 2,0 o CLR versione 1,1.</span><span class="sxs-lookup"><span data-stu-id="f118f-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="f118f-119">Tuttavia, la versione CLR 1,1 e la versione 2,0 CLR non possono essere eseguite side-by-side in-process.</span><span class="sxs-lookup"><span data-stu-id="f118f-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="f118f-120">Se nel processo non sono stati caricati Runtime, questo metodo restituisce sempre `true` .</span><span class="sxs-lookup"><span data-stu-id="f118f-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f118f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f118f-121">Requirements</span></span>  
 <span data-ttu-id="f118f-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f118f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f118f-123">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f118f-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f118f-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f118f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f118f-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f118f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f118f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f118f-126">See also</span></span>

- [<span data-ttu-id="f118f-127">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f118f-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f118f-128">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="f118f-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f118f-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="f118f-129">Hosting</span></span>](index.md)
