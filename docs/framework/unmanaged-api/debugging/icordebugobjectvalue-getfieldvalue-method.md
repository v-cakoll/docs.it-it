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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207583"
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
 in `mdFieldDef`Token che fa riferimento ai metadati che descrivono il campo.  
  
 `ppValue`  
 out Puntatore a un oggetto "ICorDebugValue" che rappresenta il valore del campo specificato.  
  
## <a name="remarks"></a>Osservazioni  
 La classe, specificata nel `pClass` parametro, deve trovarsi nella gerarchia della classe del valore dell'oggetto e il campo deve essere un campo di tale classe.  
  
 Il `GetFieldValue` metodo avrà comunque esito positivo per gli oggetti generici e le classi generiche. Se, ad esempio, \< il> di dizionario v eredita dalla stringa del dizionario \< , v> e il valore dell'oggetto è di tipo dizionario \< Int32>, il passaggio dell' `ICorDebugClass` oggetto per il dizionario \< K, v> otterrà correttamente un campo di stringa del dizionario \< , Int32>.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
