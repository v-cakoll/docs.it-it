---
title: Interfaccia ICorDebugVariableHome
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: caf6a24207be98be9afb10be2bd027b51405fa3b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396543"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="dfe59-102">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="dfe59-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="dfe59-103">Rappresenta una variabile locale o un argomento di una funzione.</span><span class="sxs-lookup"><span data-stu-id="dfe59-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfe59-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dfe59-104">Methods</span></span>  
  
|<span data-ttu-id="dfe59-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dfe59-105">Method</span></span>|<span data-ttu-id="dfe59-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfe59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfe59-107">Metodo GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="dfe59-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="dfe59-108">Ottiene l'indice di un argomento della funzione.</span><span class="sxs-lookup"><span data-stu-id="dfe59-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="dfe59-109">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="dfe59-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="dfe59-110">Ottiene l'istanza "ICorDebugCode" che contiene questo `ICorDebugVariableHome` oggetto.</span><span class="sxs-lookup"><span data-stu-id="dfe59-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="dfe59-111">Metodo GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="dfe59-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="dfe59-112">Ottiene l'intervallo nativo su cui questa variabile è attiva.</span><span class="sxs-lookup"><span data-stu-id="dfe59-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="dfe59-113">Metodo GetLocationType</span><span class="sxs-lookup"><span data-stu-id="dfe59-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="dfe59-114">Ottiene il tipo della posizione nativa della variabile.</span><span class="sxs-lookup"><span data-stu-id="dfe59-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="dfe59-115">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="dfe59-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="dfe59-116">Ottiene l'offset dal registro di base per una variabile.</span><span class="sxs-lookup"><span data-stu-id="dfe59-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="dfe59-117">Metodo GetRegister</span><span class="sxs-lookup"><span data-stu-id="dfe59-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="dfe59-118">Ottiene il registro contenente una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="dfe59-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="dfe59-119">Metodo GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="dfe59-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="dfe59-120">Ottiene l'indice di slot gestito di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="dfe59-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dfe59-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfe59-121">Example</span></span>  
 <span data-ttu-id="dfe59-122">Nel frammento di codice seguente viene utilizzato l'oggetto [interfacce icordebugcode4](icordebugcode4-interface.md) denominato `pCode4` .</span><span class="sxs-lookup"><span data-stu-id="dfe59-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="dfe59-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfe59-123">Requirements</span></span>  
 <span data-ttu-id="dfe59-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe59-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe59-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfe59-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfe59-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfe59-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfe59-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe59-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe59-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dfe59-128">See also</span></span>

- [<span data-ttu-id="dfe59-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dfe59-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dfe59-130">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="dfe59-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
