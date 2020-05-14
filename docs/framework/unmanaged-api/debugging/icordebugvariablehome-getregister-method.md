---
title: 'Metodo ICorDebugVariableHome:: getRegister'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 6cf66774209bd07426872c29c15b2225421c2b4d
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396826"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="dd70e-102">Metodo ICorDebugVariableHome:: getRegister</span><span class="sxs-lookup"><span data-stu-id="dd70e-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="dd70e-103">Ottiene il registro contenente una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="dd70e-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd70e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd70e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd70e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd70e-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="dd70e-106">out Valore di Enumerazione CorDebugRegister che indica il registro per una variabile con un tipo di posizione `VLT_REGISTER` e il registro di base per una variabile con un tipo di posizione `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="dd70e-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd70e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd70e-107">Return Value</span></span>  
 <span data-ttu-id="dd70e-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd70e-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="dd70e-109">Valore</span><span class="sxs-lookup"><span data-stu-id="dd70e-109">Value</span></span>|<span data-ttu-id="dd70e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd70e-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="dd70e-111">La variabile si trova nel registro indicato dall' `pRegister` argomento.</span><span class="sxs-lookup"><span data-stu-id="dd70e-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="dd70e-112">La variabile non si trova in un registro o in un percorso relativo al registro.</span><span class="sxs-lookup"><span data-stu-id="dd70e-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd70e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd70e-113">Requirements</span></span>  
 <span data-ttu-id="dd70e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd70e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd70e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd70e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd70e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd70e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd70e-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd70e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd70e-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dd70e-118">See also</span></span>

- [<span data-ttu-id="dd70e-119">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="dd70e-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="dd70e-120">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="dd70e-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
