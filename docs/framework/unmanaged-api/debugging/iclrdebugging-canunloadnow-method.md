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
ms.openlocfilehash: 41b2e009f8f017a72147232015ea2357ae922ca1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793643"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="02d71-102">Metodo ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="02d71-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="02d71-103">Determina se una libreria fornita da un'interfaccia [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) è ancora in uso o può essere scaricata.</span><span class="sxs-lookup"><span data-stu-id="02d71-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d71-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02d71-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d71-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02d71-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="02d71-106">in Indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="02d71-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d71-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="02d71-107">Return Value</span></span>  
 <span data-ttu-id="02d71-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="02d71-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="02d71-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02d71-109">HRESULT</span></span>|<span data-ttu-id="02d71-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02d71-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02d71-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="02d71-111">S_OK</span></span>|<span data-ttu-id="02d71-112">Il modulo a cui fa riferimento `hmodule` può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="02d71-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="02d71-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="02d71-113">S_FALSE</span></span>|<span data-ttu-id="02d71-114">Il modulo a cui fa riferimento `hmodule` è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="02d71-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="02d71-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="02d71-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="02d71-116">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="02d71-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="02d71-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="02d71-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d71-118">Note</span><span class="sxs-lookup"><span data-stu-id="02d71-118">Remarks</span></span>  
 <span data-ttu-id="02d71-119">Questo metodo verifica se tutte le istanze di `ICorDebug*` interfacce sono state rilasciate e nessun thread è attualmente in una chiamata al metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="02d71-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d71-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="02d71-120">Requirements</span></span>  
 <span data-ttu-id="02d71-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d71-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d71-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d71-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d71-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d71-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d71-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d71-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d71-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02d71-125">See also</span></span>

- [<span data-ttu-id="02d71-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="02d71-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="02d71-127">Debug</span><span class="sxs-lookup"><span data-stu-id="02d71-127">Debugging</span></span>](index.md)
