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
ms.openlocfilehash: 472e06c3a00762a7bb012fbcb525d8e0b3a9271a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162256"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="21cc3-102">Metodo IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="21cc3-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="21cc3-103">Restituisce le informazioni di visualizzazione dell'associazione corrente.</span><span class="sxs-lookup"><span data-stu-id="21cc3-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21cc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21cc3-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21cc3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21cc3-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="21cc3-106">[out, retval] Un puntatore a un safearray contenente le informazioni di visualizzazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="21cc3-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21cc3-107">Note</span><span class="sxs-lookup"><span data-stu-id="21cc3-107">Remarks</span></span>  
 <span data-ttu-id="21cc3-108">Il [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) metodo deve avere in precedenza ha avuto esito positivo e il programma deve essere interrotto da un debugger.</span><span class="sxs-lookup"><span data-stu-id="21cc3-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="21cc3-109">Il chiamante deve deallocare restituita `SAFEARRAY` memoria usando [routine](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="21cc3-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21cc3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21cc3-110">Requirements</span></span>  
 <span data-ttu-id="21cc3-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21cc3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21cc3-112">**Intestazione:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="21cc3-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="21cc3-113">**Libreria:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="21cc3-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="21cc3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21cc3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21cc3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21cc3-115">See also</span></span>

- [<span data-ttu-id="21cc3-116">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="21cc3-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="21cc3-117">Metodo InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="21cc3-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
