---
title: Metodo ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095885"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="450fc-102">Metodo ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="450fc-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="450fc-103">Ottiene il valore del campo specificato della classe specificata per il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="450fc-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="450fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="450fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="450fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="450fc-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="450fc-106">in Puntatore a un oggetto "ICorDebugClass" che rappresenta la classe per la quale ottenere il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="450fc-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="450fc-107">in Token `mdFieldDef` che fa riferimento ai metadati che descrivono il campo.</span><span class="sxs-lookup"><span data-stu-id="450fc-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="450fc-108">out Puntatore a un oggetto "ICorDebugValue" che rappresenta il valore del campo specificato.</span><span class="sxs-lookup"><span data-stu-id="450fc-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="450fc-109">Note</span><span class="sxs-lookup"><span data-stu-id="450fc-109">Remarks</span></span>  
 <span data-ttu-id="450fc-110">La classe, specificata nel parametro `pClass`, deve trovarsi nella gerarchia della classe del valore dell'oggetto e il campo deve essere un campo di tale classe.</span><span class="sxs-lookup"><span data-stu-id="450fc-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="450fc-111">Il metodo `GetFieldValue` avrà comunque esito positivo per gli oggetti generici e le classi generiche.</span><span class="sxs-lookup"><span data-stu-id="450fc-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="450fc-112">Se, ad esempio, il dizionario\<V > eredita da Dictionary\<String, V > e il valore dell'oggetto è di tipo dizionario\<Int32 >, passando l'oggetto `ICorDebugClass` per Dictionary\<K, V > otterrà correttamente un campo di Dictionary\<String, Int32 >.</span><span class="sxs-lookup"><span data-stu-id="450fc-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="450fc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="450fc-113">Requirements</span></span>  
 <span data-ttu-id="450fc-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="450fc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="450fc-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="450fc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="450fc-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="450fc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="450fc-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="450fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450fc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="450fc-118">See also</span></span>
