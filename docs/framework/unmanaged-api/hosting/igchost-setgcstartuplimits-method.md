---
title: Metodo IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 3b0c11ac9d827bd252018172e2337df653054a7b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805207"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="2f48e-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="2f48e-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="2f48e-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="2f48e-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2f48e-104">A partire da .NET Framework 4,5, è possibile impostare dimensioni del segmento e dimensioni massime 0 di generazione su valori maggiori di `DWORD` usando il metodo [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2f48e-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f48e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f48e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f48e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f48e-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="2f48e-107">in Dimensioni del segmento utilizzato dal sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2f48e-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="2f48e-108">in Dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="2f48e-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f48e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f48e-109">Remarks</span></span>  
 <span data-ttu-id="2f48e-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2f48e-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="2f48e-111">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2f48e-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f48e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f48e-112">Requirements</span></span>  
 <span data-ttu-id="2f48e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f48e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f48e-114">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="2f48e-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2f48e-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2f48e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f48e-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f48e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f48e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f48e-117">See also</span></span>

- [<span data-ttu-id="2f48e-118">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="2f48e-118">IGCHost Interface</span></span>](igchost-interface.md)
