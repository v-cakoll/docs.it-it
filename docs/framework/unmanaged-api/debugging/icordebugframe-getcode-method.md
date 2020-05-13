---
title: Metodo ICorDebugFrame::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: c8914ba1090ec5fd6540e9ead302675cb44f37e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208603"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="50e35-102">Metodo ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="50e35-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="50e35-103">Ottiene un puntatore al codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="50e35-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50e35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50e35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50e35-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="50e35-106">out Puntatore all'indirizzo di un oggetto ICorDebugCode che rappresenta il codice associato a questo frame.</span><span class="sxs-lookup"><span data-stu-id="50e35-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e35-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50e35-107">Requirements</span></span>  
 <span data-ttu-id="50e35-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e35-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e35-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50e35-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50e35-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e35-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50e35-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e35-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
