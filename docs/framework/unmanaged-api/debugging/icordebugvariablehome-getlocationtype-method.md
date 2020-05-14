---
title: 'Metodo ICorDebugVariableHome:: GetLocationType'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396567"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="45a44-102">Metodo ICorDebugVariableHome:: GetLocationType</span><span class="sxs-lookup"><span data-stu-id="45a44-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="45a44-103">Ottiene il tipo della posizione nativa della variabile.</span><span class="sxs-lookup"><span data-stu-id="45a44-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45a44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45a44-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45a44-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="45a44-106">out Puntatore al tipo della posizione nativa della variabile.</span><span class="sxs-lookup"><span data-stu-id="45a44-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="45a44-107">Per ulteriori informazioni, vedere l'enumerazione [VariableLocationType](variablelocationtype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="45a44-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a44-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45a44-108">Requirements</span></span>  
 <span data-ttu-id="45a44-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a44-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a44-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45a44-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45a44-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45a44-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45a44-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a44-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a44-113">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="45a44-113">See also</span></span>

- [<span data-ttu-id="45a44-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="45a44-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="45a44-115">Enumerazione VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="45a44-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
