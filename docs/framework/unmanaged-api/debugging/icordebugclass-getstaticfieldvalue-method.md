---
title: Metodo ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: 873dd5a1eb2c9356049d2d0c0cb495b963c2ae46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784197"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="29ae8-102">Metodo ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="29ae8-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="29ae8-103">Ottiene il valore del campo statico specificato.</span><span class="sxs-lookup"><span data-stu-id="29ae8-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ae8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29ae8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29ae8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29ae8-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="29ae8-106">in Un campo `Def` token che fa riferimento al campo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="29ae8-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="29ae8-107">in Puntatore a un oggetto ICorDebugFrame che rappresenta il frame da usare per evitare ambiguità tra il thread, il contesto o gli elementi statici del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="29ae8-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="29ae8-108">Se il campo statico è relativo a un thread, a un contesto o a un dominio dell'applicazione, il frame determinerà il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="29ae8-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="29ae8-109">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="29ae8-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29ae8-110">Note</span><span class="sxs-lookup"><span data-stu-id="29ae8-110">Remarks</span></span>  
 <span data-ttu-id="29ae8-111">Per i tipi con parametri, il valore di un campo statico è relativo alla particolare creazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="29ae8-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="29ae8-112">Se pertanto il costruttore della classe accetta parametri di tipo <xref:System.Type>, chiamare [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) anziché `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="29ae8-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ae8-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="29ae8-113">Requirements</span></span>  
 <span data-ttu-id="29ae8-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29ae8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ae8-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29ae8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29ae8-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29ae8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29ae8-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ae8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
