---
title: Metodo ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379994"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="e7fc3-102">Metodo ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="e7fc3-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="e7fc3-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugType che rappresenta il tipo di base, se presente, del tipo rappresentato dall'oggetto `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="e7fc3-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7fc3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7fc3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7fc3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7fc3-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="e7fc3-106">out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="e7fc3-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7fc3-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e7fc3-107">Remarks</span></span>  
 <span data-ttu-id="e7fc3-108">La ricerca del tipo di base per un tipo è utile per implementare funzionalità comuni del debugger, ad esempio la stampa di tutti i campi di un oggetto o delle relative classi padre.</span><span class="sxs-lookup"><span data-stu-id="e7fc3-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7fc3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7fc3-109">Requirements</span></span>  
 <span data-ttu-id="e7fc3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7fc3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7fc3-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7fc3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7fc3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7fc3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7fc3-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7fc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
