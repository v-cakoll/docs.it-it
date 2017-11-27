---
title: Metodo IBindingDisplay::InitializeForProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IBindingDisplay.InitializeForProcess
api_location: diasymreader.dll
api_type: COM
f1_keywords: IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e5ab3bb38d23e5841a347a348a09deb3b5639962
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="17327-102">Metodo IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="17327-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="17327-103">Inizializza il [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="17327-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17327-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17327-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17327-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17327-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="17327-106">[in] Identificatore di processo.</span><span class="sxs-lookup"><span data-stu-id="17327-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17327-107">Note</span><span class="sxs-lookup"><span data-stu-id="17327-107">Remarks</span></span>  
 <span data-ttu-id="17327-108">Il debugger chiama il `InitializeForProcess` metodo al momento della creazione per inizializzare la visualizzazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="17327-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="17327-109">`InitializeForProcess`deve essere chiamato in fase di creazione prima di qualsiasi altro metodo per `IBindingDisplay` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="17327-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17327-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17327-110">Requirements</span></span>  
 <span data-ttu-id="17327-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17327-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17327-112">**Intestazione:** BindingDisplay. H</span><span class="sxs-lookup"><span data-stu-id="17327-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="17327-113">**Libreria:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="17327-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="17327-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17327-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17327-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17327-115">See Also</span></span>  
 [<span data-ttu-id="17327-116">IBindingDisplay (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="17327-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
