---
title: Metodo ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 178d1df7e6c8246b18afed442e944c49051b6597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209266"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="a26f7-102">Metodo ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="a26f7-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="a26f7-103">Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="a26f7-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a26f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a26f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a26f7-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="a26f7-106">in Valore [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) che specifica l'indirizzo iniziale del segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a26f7-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="a26f7-107">out Puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta un segmento di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a26f7-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a26f7-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a26f7-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a26f7-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a26f7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a26f7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a26f7-110">Requirements</span></span>  
 <span data-ttu-id="a26f7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a26f7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a26f7-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a26f7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a26f7-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a26f7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a26f7-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a26f7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a26f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a26f7-115">See also</span></span>

- [<span data-ttu-id="a26f7-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="a26f7-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="a26f7-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a26f7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
