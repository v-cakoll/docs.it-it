---
title: Metodo ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 1588728f486ffb3db583439de05aff34e3dc59f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792274"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="0fd04-102">Metodo ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="0fd04-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="0fd04-103">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="0fd04-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd04-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fd04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fd04-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fd04-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="0fd04-106">in Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che specifica l'indirizzo iniziale del segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0fd04-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="0fd04-107">out Puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta un segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0fd04-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fd04-108">Note</span><span class="sxs-lookup"><span data-stu-id="0fd04-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fd04-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0fd04-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fd04-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0fd04-110">Requirements</span></span>  
 <span data-ttu-id="0fd04-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fd04-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fd04-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fd04-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fd04-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fd04-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fd04-114">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fd04-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd04-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fd04-115">See also</span></span>

- [<span data-ttu-id="0fd04-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="0fd04-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="0fd04-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0fd04-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
