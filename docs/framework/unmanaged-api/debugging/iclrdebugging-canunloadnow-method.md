---
title: Metodo ICLRDebugging::CanUnloadNow
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 16d15101534b88d7da4093dab73b48b5c09a192c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860396"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="64fed-102">Metodo ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="64fed-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="64fed-103">Determina se una libreria fornita da un'interfaccia [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) è ancora in uso o può essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="64fed-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64fed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64fed-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64fed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64fed-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="64fed-106">in Indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="64fed-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64fed-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64fed-107">Return Value</span></span>  
 <span data-ttu-id="64fed-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="64fed-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="64fed-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64fed-109">HRESULT</span></span>|<span data-ttu-id="64fed-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64fed-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64fed-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="64fed-111">S_OK</span></span>|<span data-ttu-id="64fed-112">Il modulo a `hmodule` cui fa riferimento può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="64fed-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="64fed-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="64fed-113">S_FALSE</span></span>|<span data-ttu-id="64fed-114">Il modulo a cui fa riferimento `hmodule` è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="64fed-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="64fed-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="64fed-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="64fed-116">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="64fed-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="64fed-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="64fed-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64fed-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="64fed-118">Remarks</span></span>  
 <span data-ttu-id="64fed-119">Questo metodo verifica se tutte le istanze delle `ICorDebug*` interfacce sono state rilasciate e nessun thread è attualmente in una chiamata al metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64fed-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64fed-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64fed-120">Requirements</span></span>  
 <span data-ttu-id="64fed-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64fed-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64fed-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64fed-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64fed-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64fed-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64fed-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64fed-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64fed-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64fed-125">See also</span></span>

- [<span data-ttu-id="64fed-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="64fed-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="64fed-127">Debug</span><span class="sxs-lookup"><span data-stu-id="64fed-127">Debugging</span></span>](index.md)
