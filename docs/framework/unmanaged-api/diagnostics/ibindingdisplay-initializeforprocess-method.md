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
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197875"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="6993b-102">Metodo IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="6993b-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="6993b-103">Inizializza la [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="6993b-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6993b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6993b-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6993b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6993b-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="6993b-106">[in] L'identificatore di processo.</span><span class="sxs-lookup"><span data-stu-id="6993b-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6993b-107">Note</span><span class="sxs-lookup"><span data-stu-id="6993b-107">Remarks</span></span>  
 <span data-ttu-id="6993b-108">Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="6993b-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="6993b-109">`InitializeForProcess` deve essere chiamato in fase di creazione della prima di qualsiasi altro metodo su `IBindingDisplay` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6993b-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6993b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6993b-110">Requirements</span></span>  
 <span data-ttu-id="6993b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6993b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6993b-112">**Intestazione:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="6993b-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="6993b-113">**Libreria:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="6993b-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="6993b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6993b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6993b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6993b-115">See also</span></span>

- [<span data-ttu-id="6993b-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="6993b-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
