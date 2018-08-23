---
title: Metodo IBindingDisplay::GetCurrentDisplay
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 889456f08c967c807b4d3d09508af000035ebdaf
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755080"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="ae04d-102">Metodo IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="ae04d-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="ae04d-103">Restituisce le informazioni di visualizzazione dell'associazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ae04d-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae04d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae04d-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae04d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae04d-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="ae04d-106">[out, retval] Un puntatore a un safearray contenente le informazioni di visualizzazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="ae04d-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae04d-107">Note</span><span class="sxs-lookup"><span data-stu-id="ae04d-107">Remarks</span></span>  
 <span data-ttu-id="ae04d-108">Il [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) metodo deve avere in precedenza ha avuto esito positivo e il programma deve essere interrotto da un debugger.</span><span class="sxs-lookup"><span data-stu-id="ae04d-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="ae04d-109">Il chiamante deve deallocare restituita `SAFEARRAY` memoria usando [routine](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="ae04d-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae04d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae04d-110">Requirements</span></span>  
 <span data-ttu-id="ae04d-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae04d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae04d-112">**Intestazione:** BindingDisplay. H</span><span class="sxs-lookup"><span data-stu-id="ae04d-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="ae04d-113">**Libreria:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="ae04d-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="ae04d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae04d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae04d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae04d-115">See Also</span></span>  
 [<span data-ttu-id="ae04d-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="ae04d-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="ae04d-117">Metodo InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="ae04d-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
