---
title: Metodo ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 5d01ab0b6b5d489b2181056129e22661a50108a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084853"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>Metodo ICorDebugEval2::NewParameterizedObject
Crea un'istanza di un nuovo oggetto di tipo con parametri e chiama il metodo del costruttore dell'oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pConstructor`  
 in Puntatore a un oggetto ICorDebugFunction che rappresenta il costruttore dell'oggetto di cui creare un'istanza.  
  
 `nTypeArgs`  
 in Numero di argomenti di tipo passati.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto di cui viene creata un'istanza.  
  
 `nArgs`  
 in Numero di argomenti passati al costruttore.  
  
 `ppArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugValue che rappresenta un valore di argomento passato al costruttore.  
  
## <a name="remarks"></a>Note  
 Il costruttore dell'oggetto può prendere <xref:System.Type> parametri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
