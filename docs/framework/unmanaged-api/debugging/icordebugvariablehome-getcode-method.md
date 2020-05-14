---
title: 'Metodo ICorDebugVariableHome:: GetCode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396597"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="65bfe-102">Metodo ICorDebugVariableHome:: GetCode</span><span class="sxs-lookup"><span data-stu-id="65bfe-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="65bfe-103">Ottiene l'istanza "ICorDebugCode" che contiene questo oggetto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="65bfe-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65bfe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65bfe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65bfe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65bfe-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="65bfe-106">out Puntatore all'indirizzo dell'istanza "ICorDebugCode" che contiene questo oggetto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="65bfe-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65bfe-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65bfe-107">Requirements</span></span>  
 <span data-ttu-id="65bfe-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65bfe-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65bfe-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65bfe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65bfe-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65bfe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65bfe-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65bfe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bfe-112">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="65bfe-112">See also</span></span>

- [<span data-ttu-id="65bfe-113">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="65bfe-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
