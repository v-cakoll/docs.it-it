---
title: Metodo ICorDebugFunction::GetLocalVarSigToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
ms.openlocfilehash: a923701b05f7d283c4fd464d470fb0c9243c1bd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213608"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="71220-102">Metodo ICorDebugFunction::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="71220-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="71220-103">Ottiene il token di metadati per la firma della variabile locale della funzione rappresentata da questa istanza di ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="71220-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71220-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71220-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71220-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71220-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="71220-106">out Puntatore al `mdSignature` token per la firma della variabile locale di questa funzione oppure `mdSignatureNil` se questa funzione non ha variabili locali.</span><span class="sxs-lookup"><span data-stu-id="71220-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71220-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71220-107">Requirements</span></span>  
 <span data-ttu-id="71220-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71220-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71220-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71220-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71220-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71220-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71220-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71220-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
