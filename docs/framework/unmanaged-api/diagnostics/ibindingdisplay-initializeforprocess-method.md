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
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775956"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="05aa3-102">Metodo IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="05aa3-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="05aa3-103">Inizializza la [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="05aa3-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05aa3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05aa3-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05aa3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05aa3-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="05aa3-106">[in] L'identificatore di processo.</span><span class="sxs-lookup"><span data-stu-id="05aa3-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05aa3-107">Note</span><span class="sxs-lookup"><span data-stu-id="05aa3-107">Remarks</span></span>  
 <span data-ttu-id="05aa3-108">Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="05aa3-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="05aa3-109">`InitializeForProcess` deve essere chiamato in fase di creazione della prima di qualsiasi altro metodo su `IBindingDisplay` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="05aa3-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05aa3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05aa3-110">Requirements</span></span>  
 <span data-ttu-id="05aa3-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05aa3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05aa3-112">**Intestazione:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="05aa3-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="05aa3-113">**Libreria:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="05aa3-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="05aa3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05aa3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05aa3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05aa3-115">See also</span></span>

- [<span data-ttu-id="05aa3-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="05aa3-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
