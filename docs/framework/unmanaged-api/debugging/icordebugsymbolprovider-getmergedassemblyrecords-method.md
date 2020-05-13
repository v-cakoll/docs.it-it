---
title: Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379630"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="7b0c3-102">Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="7b0c3-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="7b0c3-103">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b0c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b0c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b0c3-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="7b0c3-106">[in] Numero di record dei simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="7b0c3-107">[out] Puntatore al numero di record dei simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="7b0c3-108">Puntatore a una matrice di oggetti [Metodo icordebugmergedassemblyrecord](icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7b0c3-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b0c3-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7b0c3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b0c3-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b0c3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b0c3-111">Requirements</span></span>  
 <span data-ttu-id="7b0c3-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b0c3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b0c3-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b0c3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b0c3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b0c3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b0c3-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b0c3-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0c3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b0c3-116">See also</span></span>

- [<span data-ttu-id="7b0c3-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="7b0c3-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="7b0c3-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7b0c3-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
