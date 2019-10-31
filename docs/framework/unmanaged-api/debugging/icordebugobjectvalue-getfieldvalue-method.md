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
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Metodo ICorDebugObjectValue::GetFieldValue
Ottiene il valore del campo specificato della classe specificata per il valore dell'oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClass`  
 in Puntatore a un oggetto "ICorDebugClass" che rappresenta la classe per la quale ottenere il valore del campo.  
  
 `fieldDef`  
 in Token `mdFieldDef` che fa riferimento ai metadati che descrivono il campo.  
  
 `ppValue`  
 out Puntatore a un oggetto "ICorDebugValue" che rappresenta il valore del campo specificato.  
  
## <a name="remarks"></a>Note  
 La classe, specificata nel parametro `pClass`, deve trovarsi nella gerarchia della classe del valore dell'oggetto e il campo deve essere un campo di tale classe.  
  
 Il metodo `GetFieldValue` avrà comunque esito positivo per gli oggetti generici e le classi generiche. Se, ad esempio, il dizionario\<V > eredita da Dictionary\<String, V > e il valore dell'oggetto è di tipo dizionario\<Int32 >, passando l'oggetto `ICorDebugClass` per Dictionary\<K, V > otterrà correttamente un campo di Dictionary\<String, Int32 >.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
