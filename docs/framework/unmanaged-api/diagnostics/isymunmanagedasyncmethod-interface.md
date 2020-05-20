---
title: Interfaccia ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: fef1af75587b889afad9cb5b93d0cd722294006b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441812"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="c46b6-102">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="c46b6-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="c46b6-103">Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c46b6-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="c46b6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c46b6-105">Methods</span></span>  
 <span data-ttu-id="c46b6-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="c46b6-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="c46b6-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="c46b6-107">Method</span></span>|<span data-ttu-id="c46b6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c46b6-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c46b6-109">Metodo GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="c46b6-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="c46b6-110">Vedere il [Metodo DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="c46b6-111">Metodo GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="c46b6-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="c46b6-112">Vedere il [Metodo DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="c46b6-113">Metodo GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="c46b6-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="c46b6-114">Vedere il [Metodo DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="c46b6-115">Metodo GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="c46b6-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="c46b6-116">Vedere il [Metodo DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="c46b6-117">Metodo HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="c46b6-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="c46b6-118">Vedere il [Metodo DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="c46b6-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="c46b6-119">Metodo IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="c46b6-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="c46b6-120">Verifica se il metodo contiene informazioni asincrone o meno.</span><span class="sxs-lookup"><span data-stu-id="c46b6-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="c46b6-121">Se questo metodo restituisce `FALSE` , non è valido chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c46b6-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="c46b6-122">`E_UNEXPECTED`In questo caso verranno restituiti tutti.</span><span class="sxs-lookup"><span data-stu-id="c46b6-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c46b6-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c46b6-123">Requirements</span></span>  
 <span data-ttu-id="c46b6-124">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c46b6-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46b6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c46b6-125">See also</span></span>

- [<span data-ttu-id="c46b6-126">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c46b6-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
