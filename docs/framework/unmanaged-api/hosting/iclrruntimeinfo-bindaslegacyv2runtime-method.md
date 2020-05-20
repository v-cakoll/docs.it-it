---
title: Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703901"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="80cc6-102">Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="80cc6-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="80cc6-103">Associa il runtime corrente per tutte le decisioni relative ai criteri di attivazione della versione 2 di Common Language Runtime legacy (CLR).</span><span class="sxs-lookup"><span data-stu-id="80cc6-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cc6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80cc6-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="80cc6-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80cc6-105">Return Value</span></span>  
 <span data-ttu-id="80cc6-106">Questo metodo restituisce i valori HRESULT specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="80cc6-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="80cc6-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80cc6-107">HRESULT</span></span>|<span data-ttu-id="80cc6-108">Description</span><span class="sxs-lookup"><span data-stu-id="80cc6-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80cc6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="80cc6-109">S_OK</span></span>|<span data-ttu-id="80cc6-110">Associazione riuscita oppure il runtime è già stato associato come runtime legacy dei criteri di attivazione di CLR versione 2.</span><span class="sxs-lookup"><span data-stu-id="80cc6-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="80cc6-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="80cc6-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="80cc6-112">Un runtime diverso era già associato ai criteri di attivazione di CLR versione 2 Legacy.</span><span class="sxs-lookup"><span data-stu-id="80cc6-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80cc6-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="80cc6-113">Remarks</span></span>  
 <span data-ttu-id="80cc6-114">Se il runtime corrente è già associato a tutte le decisioni relative ai criteri di attivazione di CLR versione 2 (ad esempio, usando l' `useLegacyV2RuntimeActivationPolicy` attributo nell' [ \< elemento> di avvio](../../configure-apps/file-schema/startup/startup-element.md) nel file di configurazione), questo metodo non restituisce un risultato di errore, ma il risultato è S_OK, così come sarebbe se il metodo avesse associato correttamente i criteri di attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="80cc6-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80cc6-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80cc6-115">Requirements</span></span>  
 <span data-ttu-id="80cc6-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80cc6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80cc6-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="80cc6-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80cc6-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="80cc6-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80cc6-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80cc6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cc6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cc6-120">See also</span></span>

- [<span data-ttu-id="80cc6-121">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="80cc6-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="80cc6-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="80cc6-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="80cc6-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="80cc6-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="80cc6-124">\<Elemento> di avvio</span><span class="sxs-lookup"><span data-stu-id="80cc6-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
