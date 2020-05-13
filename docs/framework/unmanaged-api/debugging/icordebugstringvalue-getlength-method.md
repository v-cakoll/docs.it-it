---
title: Metodo ICorDebugStringValue::GetLength
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: 945e4ac88634c9103a722a180a4fe92a554ca53b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378888"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="31622-102">Metodo ICorDebugStringValue::GetLength</span><span class="sxs-lookup"><span data-stu-id="31622-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="31622-103">Ottiene il numero di caratteri nella stringa a cui fa riferimento questo ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="31622-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31622-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31622-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31622-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31622-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="31622-106">out Puntatore a un valore che specifica la lunghezza della stringa a cui fa riferimento questo `ICorDebugStringValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="31622-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31622-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31622-107">Requirements</span></span>  
 <span data-ttu-id="31622-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31622-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31622-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31622-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31622-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31622-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31622-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31622-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
