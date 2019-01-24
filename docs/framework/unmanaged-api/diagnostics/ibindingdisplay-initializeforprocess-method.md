---
title: Metodo IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e701b49a99b548bbfd0cd6c583b7069bca2142b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711054"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="d0c74-102">Metodo IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="d0c74-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="d0c74-103">Inizializza la [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="d0c74-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0c74-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0c74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0c74-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="d0c74-106">[in] L'identificatore di processo.</span><span class="sxs-lookup"><span data-stu-id="d0c74-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0c74-107">Note</span><span class="sxs-lookup"><span data-stu-id="d0c74-107">Remarks</span></span>  
 <span data-ttu-id="d0c74-108">Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="d0c74-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="d0c74-109">`InitializeForProcess` deve essere chiamato in fase di creazione della prima di qualsiasi altro metodo su `IBindingDisplay` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="d0c74-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0c74-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0c74-110">Requirements</span></span>  
 <span data-ttu-id="d0c74-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0c74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0c74-112">**Intestazione:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="d0c74-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d0c74-113">**Libreria:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="d0c74-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d0c74-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0c74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c74-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0c74-115">See also</span></span>
- [<span data-ttu-id="d0c74-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="d0c74-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
