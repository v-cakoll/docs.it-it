---
title: Metodo IBindingDisplay::GetCurrentDisplay
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IBindingDisplay.GetCurrentDisplay
api_location: diasymreader.dll
api_type: COM
f1_keywords: IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4e9ba86efe44fdcfb717970bf664198068d89d36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="7974a-102">Metodo IBindingDisplay::GetCurrentDisplay</span><span class="sxs-lookup"><span data-stu-id="7974a-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="7974a-103">Restituisce le informazioni di visualizzazione di associazione corrente.</span><span class="sxs-lookup"><span data-stu-id="7974a-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7974a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7974a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7974a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7974a-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="7974a-106">[out, retval] Un puntatore a un safearray contenente le informazioni di visualizzazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="7974a-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7974a-107">Note</span><span class="sxs-lookup"><span data-stu-id="7974a-107">Remarks</span></span>  
 <span data-ttu-id="7974a-108">Il [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) metodo InitializeForProcess deve essere in precedenza, e il programma deve essere interrotto da un debugger.</span><span class="sxs-lookup"><span data-stu-id="7974a-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="7974a-109">Il chiamante deve deallocare restituito `SAFEARRAY` memoria tramite [tuttavia](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span><span class="sxs-lookup"><span data-stu-id="7974a-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7974a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7974a-110">Requirements</span></span>  
 <span data-ttu-id="7974a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7974a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7974a-112">**Intestazione:** BindingDisplay. H</span><span class="sxs-lookup"><span data-stu-id="7974a-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="7974a-113">**Libreria:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="7974a-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="7974a-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7974a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7974a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7974a-115">See Also</span></span>  
 [<span data-ttu-id="7974a-116">IBindingDisplay (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7974a-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="7974a-117">InitializeForProcess (metodo)</span><span class="sxs-lookup"><span data-stu-id="7974a-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
