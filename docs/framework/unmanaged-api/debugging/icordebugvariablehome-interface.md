---
title: Interfaccia ICorDebugVariableHome
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea8f4033a6b0878288c49d6f6d964eb40675162d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="75853-102">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="75853-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="75853-103">Rappresenta una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="75853-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75853-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="75853-104">Methods</span></span>  
  
|<span data-ttu-id="75853-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="75853-105">Method</span></span>|<span data-ttu-id="75853-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75853-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75853-107">Metodo GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="75853-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="75853-108">Ottiene l'indice di un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="75853-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="75853-109">GetCode (metodo)</span><span class="sxs-lookup"><span data-stu-id="75853-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="75853-110">Ottiene l'istanza "ICorDebugCode" che contiene questo `ICorDebugVariableHome` oggetto.</span><span class="sxs-lookup"><span data-stu-id="75853-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="75853-111">Metodo GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="75853-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="75853-112">Ottiene l'intervallo nativo su cui questa variabile è in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="75853-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="75853-113">Metodo GetLocationType</span><span class="sxs-lookup"><span data-stu-id="75853-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="75853-114">Ottiene il tipo di posizione nativo della variabile.</span><span class="sxs-lookup"><span data-stu-id="75853-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="75853-115">GetOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="75853-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="75853-116">Ottiene l'offset del Registro di base per una variabile.</span><span class="sxs-lookup"><span data-stu-id="75853-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="75853-117">Metodo GetRegister</span><span class="sxs-lookup"><span data-stu-id="75853-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="75853-118">Ottiene il registro contenente una variabile con un tipo di posizione di `VLT_REGISTER`e la registrazione di base per una variabile con un tipo di posizione di `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="75853-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="75853-119">Metodo GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="75853-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="75853-120">Ottiene l'indice dello slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="75853-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75853-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="75853-121">Example</span></span>  
 <span data-ttu-id="75853-122">Il frammento di codice seguente utilizza il [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) oggetto denominato `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="75853-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="75853-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75853-123">Requirements</span></span>  
 <span data-ttu-id="75853-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75853-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75853-125">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="75853-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75853-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75853-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75853-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75853-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75853-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75853-128">See Also</span></span>  
 [<span data-ttu-id="75853-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="75853-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="75853-130">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="75853-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
