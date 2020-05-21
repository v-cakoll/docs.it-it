---
title: Metodo ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 88abdbc62c8b27f48c5629afb99ab6e30ee67e00
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762266"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="a3d03-102">Metodo ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3d03-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="a3d03-103">Ottiene un oggetto che consente all'host di specificare la configurazione di callback del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a3d03-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3d03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d03-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3d03-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="a3d03-106">out Puntatore all'indirizzo di un oggetto [ICorConfiguration](icorconfiguration-interface.md) che può essere utilizzato per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="a3d03-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d03-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a3d03-107">Remarks</span></span>  
 <span data-ttu-id="a3d03-108">CLR deve essere configurato prima dell'inizializzazione. in caso contrario, il `GetConfiguration` metodo restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="a3d03-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d03-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3d03-109">Requirements</span></span>  
 <span data-ttu-id="a3d03-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3d03-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d03-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3d03-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3d03-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a3d03-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3d03-113">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a3d03-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d03-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3d03-114">See also</span></span>

- [<span data-ttu-id="a3d03-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a3d03-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
