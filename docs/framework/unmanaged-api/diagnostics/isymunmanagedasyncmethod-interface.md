---
title: Interfaccia ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd7b351de8e82f9fdbe623505f86b54f6eba68d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694867"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="75817-102">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="75817-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="75817-103">Questa interfaccia è il complemento di lettura per il [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="75817-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75817-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75817-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="75817-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="75817-105">Methods</span></span>  
 <span data-ttu-id="75817-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="75817-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="75817-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="75817-107">Method</span></span>|<span data-ttu-id="75817-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75817-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75817-109">Metodo GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="75817-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="75817-110">Visualizzare [metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="75817-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="75817-111">Metodo GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="75817-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="75817-112">Visualizzare [metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="75817-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="75817-113">Metodo GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="75817-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="75817-114">Visualizzare [metodo DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="75817-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="75817-115">Metodo GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="75817-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="75817-116">Visualizzare [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="75817-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="75817-117">Metodo HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="75817-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="75817-118">Visualizzare [metodo DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="75817-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="75817-119">Metodo IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="75817-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="75817-120">Controlla se il metodo contiene le informazioni di async o meno.</span><span class="sxs-lookup"><span data-stu-id="75817-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="75817-121">Se questo metodo restituisce `FALSE` quindi non è consentito chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75817-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="75817-122">Restituirà tutti `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="75817-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75817-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75817-123">Requirements</span></span>  
 <span data-ttu-id="75817-124">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75817-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75817-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75817-125">See also</span></span>
- [<span data-ttu-id="75817-126">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="75817-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
