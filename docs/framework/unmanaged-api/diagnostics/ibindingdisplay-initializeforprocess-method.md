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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442150"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="74c60-102">Metodo IBindingDisplay::InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="74c60-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="74c60-103">Inizializza l'oggetto [IBindingDisplay](ibindingdisplay-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="74c60-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74c60-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74c60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74c60-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="74c60-106">in Identificatore del processo.</span><span class="sxs-lookup"><span data-stu-id="74c60-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74c60-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="74c60-107">Remarks</span></span>  
 <span data-ttu-id="74c60-108">Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="74c60-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="74c60-109">`InitializeForProcess`deve essere chiamato in fase di creazione prima che venga chiamato un altro metodo su `IBindingDisplay` .</span><span class="sxs-lookup"><span data-stu-id="74c60-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c60-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74c60-110">Requirements</span></span>  
 <span data-ttu-id="74c60-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c60-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c60-112">**Intestazione:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="74c60-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="74c60-113">**Libreria:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="74c60-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="74c60-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c60-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74c60-115">See also</span></span>

- [<span data-ttu-id="74c60-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="74c60-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
