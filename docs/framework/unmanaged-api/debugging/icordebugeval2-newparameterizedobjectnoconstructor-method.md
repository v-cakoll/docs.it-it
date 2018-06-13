---
title: Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aad5a285fc2280dc062b0f4cbb69977a7e605e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412769"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a>Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza tentare di chiamare un metodo del costruttore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pClass`  
 [in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto deve essere creata un'istanza.  
  
 `nTypeArgs`  
 [in] Il numero di argomenti di tipo passato.  
  
 `ppTypeArgs`  
 [in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto che viene creata un'istanza.  
  
## <a name="remarks"></a>Note  
 Il `NewParameterizedObjectNoConstructor` metodo avrà esito negativo se un numero errato di argomenti di tipo o vengono passati i tipi di argomenti di tipo errati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
