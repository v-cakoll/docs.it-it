---
title: Interfaccia ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cefad27d8b9314b45dec6100e35a54990fb591c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427999"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="c39fa-102">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="c39fa-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="c39fa-103">Questa interfaccia rappresenta il complemento di lettura per [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c39fa-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="c39fa-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c39fa-105">Methods</span></span>  
 <span data-ttu-id="c39fa-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="c39fa-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="c39fa-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="c39fa-107">Method</span></span>|<span data-ttu-id="c39fa-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c39fa-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c39fa-109">Metodo GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="c39fa-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="c39fa-110">Vedere [metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="c39fa-111">Metodo GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="c39fa-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="c39fa-112">Vedere [metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="c39fa-113">Metodo GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="c39fa-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="c39fa-114">Vedere [metodo DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="c39fa-115">Metodo GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="c39fa-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="c39fa-116">Vedere [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="c39fa-117">Metodo HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="c39fa-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="c39fa-118">Vedere [metodo DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="c39fa-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="c39fa-119">Metodo IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="c39fa-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="c39fa-120">Controlla se il metodo dispone di informazioni asincrono o meno.</span><span class="sxs-lookup"><span data-stu-id="c39fa-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="c39fa-121">Se questo metodo restituisce `FALSE` quindi non è possibile chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c39fa-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="c39fa-122">Avrà tutte restituito `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="c39fa-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c39fa-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c39fa-123">Requirements</span></span>  
 <span data-ttu-id="c39fa-124">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c39fa-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39fa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c39fa-125">See Also</span></span>  
 [<span data-ttu-id="c39fa-126">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c39fa-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
