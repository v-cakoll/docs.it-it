---
title: Metodo ICorDebugClass2::GetParameterizedType
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 329bcee441b395982a8a8b539c0a938fa8170b14
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894050"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Metodo ICorDebugClass2::GetParameterizedType
Ottiene la dichiarazione del tipo per questa classe.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 in Valore dell'enumerazione CorElementType che specifica il tipo di elemento per questa classe: impostare questo valore su ELEMENT_TYPE_VALUETYPE se il ICorDebugClass2 rappresenta un tipo di valore. Impostare questo valore su ELEMENT_TYPE_CLASS se l' `ICorDebugClass2` oggetto rappresenta un tipo complesso.  
  
 `nTypeArgs`  
 in Il numero di parametri di tipo, se il tipo è generico. Il numero di parametri di tipo (se presente) deve corrispondere al numero richiesto dalla classe.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un parametro di tipo. Se la classe non è generica, questo valore è null.  
  
 `ppType`  
 out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la dichiarazione del tipo. Questo oggetto è equivalente a un <xref:System.Type> oggetto nel codice gestito.  
  
## <a name="remarks"></a>Osservazioni  
 Se la classe non è generica, ovvero se non ha parametri di tipo, `GetParameterizedType` ottiene semplicemente l'oggetto di tipo runtime corrispondente alla classe. Il `elementType` parametro deve essere impostato sul tipo di elemento corretto per la classe: ELEMENT_TYPE_VALUETYPE se la classe è un tipo di valore. in caso contrario, ELEMENT_TYPE_CLASS.  
  
 Se la classe accetta parametri di tipo (ad esempio `ArrayList<T>`,), è possibile `GetParameterizedType` usare per costruire un oggetto tipo per un tipo di cui è `ArrayList<int>`stata creata un'istanza, ad esempio.  
  
## <a name="background-information"></a>Informazioni di base  
 Nelle versioni .NET Framework 1,0 e 1,1, è possibile eseguire il mapping diretto di ogni tipo nei metadati a un tipo del processo in esecuzione. Pertanto, un tipo di metadati e un tipo di runtime hanno una sola rappresentazione nel processo in esecuzione. Tuttavia, è possibile eseguire il mapping di un tipo generico nei metadati a numerose creazioni di istanze diverse del tipo nel processo in esecuzione. Ad esempio, `SortedList<K,V>` il tipo di metadati può essere `SortedList<String, EmployeeRecord>`mappato a, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`e così via. Pertanto, è necessario un modo per gestire la creazione dell'istanza del tipo.  
  
 Il .NET Framework versione 2,0 introduce l' `ICorDebugType` interfaccia. Per un tipo generico, un `ICorDebugClass` oggetto `ICorDebugClass2` o rappresenta il tipo privo di istanze`SortedList<K,V>`() e un `ICorDebugType` oggetto rappresenta i vari tipi di cui è stata creata un'istanza. Dato un `ICorDebugClass` oggetto `ICorDebugClass2` o, è possibile creare un `ICorDebugType` oggetto per qualsiasi creazione di istanza chiamando il `ICorDebugClass2::GetParameterizedType` metodo. È anche possibile creare un `ICorDebugType` oggetto per un tipo semplice, ad esempio Int32, o per un tipo non generico.  
  
 L'introduzione dell' `ICorDebugType` oggetto per rappresentare la nozione di runtime di un tipo ha un effetto ripple nell'API. Le funzioni che in precedenza `ICorDebugClass` accettano `ICorDebugClass2` un oggetto o o `CorElementType` addirittura un valore sono generalizzate per `ICorDebugType` l'esecuzione di un oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
