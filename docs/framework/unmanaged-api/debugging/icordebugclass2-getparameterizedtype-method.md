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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1734ca91fd48cc15b8dbf25f11518ed0455b6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750774"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Metodo ICorDebugClass2::GetParameterizedType
Ottiene la dichiarazione del tipo per questa classe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo di elemento per questa classe: Impostare questo valore su ELEMENT_TYPE_VALUETYPE se questo ICorDebugClass2 rappresenta un tipo di valore. Impostare questo valore su ELEMENT_TYPE_CLASS se questa `ICorDebugClass2` rappresenta un tipo complesso.  
  
 `nTypeArgs`  
 [in] Il numero di parametri di tipo, se il tipo è generico. Il numero di parametri di tipo (se presente) deve corrispondere al numero richiesto dalla classe.  
  
 `ppTypeArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un parametro di tipo. Se la classe non generica, questo valore è null.  
  
 `ppType`  
 [out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la dichiarazione del tipo. Questo oggetto è equivalente a un <xref:System.Type> oggetto nel codice gestito.  
  
## <a name="remarks"></a>Note  
 Se la classe non generica, vale a dire, se non ha parametri di tipo, `GetParameterizedType` semplicemente Ottiene l'oggetto di tipo runtime corrispondente alla classe. Il `elementType` parametro deve essere impostato per il tipo di elemento corretto per la classe: ELEMENT_TYPE_VALUETYPE se la classe è un tipo di valore. in caso contrario, ELEMENT_TYPE_CLASS.  
  
 Se la classe accetta i parametri di tipo (ad esempio, `ArrayList<T>`), è possibile usare `GetParameterizedType` per costruire un oggetto di tipo per un tipo con istanze, ad esempio `ArrayList<int>`.  
  
## <a name="background-information"></a>Informazioni di base  
 Nelle versioni 1.0 e 1.1 di .NET Framework, ogni tipo nei metadati è stato possibile eseguire direttamente il mapping a un tipo di processo in esecuzione. Di conseguenza, un tipo di metadati e un tipo di runtime aveva una sola rappresentazione nel processo in esecuzione. Tuttavia, un tipo generico nei metadati può essere mappato a molte istanze diverse del tipo nel processo in esecuzione. Ad esempio, il tipo di metadati `SortedList<K,V>` può eseguire il mapping a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`e così via. Di conseguenza, è necessario un modo per gestire l'istanza del tipo.  
  
 .NET Framework versione 2.0 introduce il `ICorDebugType` interfaccia. Per un tipo generico, un `ICorDebugClass` oppure `ICorDebugClass2` rappresenta il tipo privo di istanze (`SortedList<K,V>`) e un `ICorDebugType` oggetto rappresenta i vari tipi di istanziati. Dato un `ICorDebugClass` oppure `ICorDebugClass2` dell'oggetto, è possibile creare un `ICorDebugType` oggetto per ogni istanza creata chiamando il `ICorDebugClass2::GetParameterizedType` (metodo). È anche possibile creare un `ICorDebugType` oggetto per un tipo semplice, ad esempio Int32, o per un tipo non generico.  
  
 L'introduzione del `ICorDebugType` oggetto per rappresentare la nozione di fase di esecuzione di un tipo ha un effetto domino in tutta l'API. Funzioni che in passato richiedeva un `ICorDebugClass` oppure `ICorDebugClass2` dell'oggetto o persino una `CorElementType` valore sono generalizzati per sfruttare un `ICorDebugType` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
