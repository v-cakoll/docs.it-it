---
title: Metodo ICorDebugClass2::GetParameterizedType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0df76f43ad037a4681f985e99401cb8c7f5a2ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo di elemento per questa classe: impostare questo valore su ELEMENT_TYPE_VALUETYPE se questo ICorDebugClass2 rappresenta un tipo di valore. Impostare questo valore su ELEMENT_TYPE_CLASS se questo `ICorDebugClass2` rappresenta un tipo complesso.  
  
 `nTypeArgs`  
 [in] Il numero di parametri di tipo, se il tipo è generico. Il numero di parametri di tipo (se presente) deve corrispondere al numero richiesto dalla classe.  
  
 `ppTypeArgs`  
 [in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un parametro di tipo. Se la classe non è generico, questo valore è null.  
  
 `ppType`  
 [out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la dichiarazione del tipo. Questo oggetto è equivalente a un <xref:System.Type> oggetto nel codice gestito.  
  
## <a name="remarks"></a>Note  
 Se la classe non generica, vale a dire, se non ha parametri di tipo, `GetParameterizedType` Ottiene semplicemente l'oggetto di tipo runtime corrispondente alla classe. Il `elementType` parametro deve essere impostato per il tipo di elemento appropriato per la classe: ELEMENT_TYPE_VALUETYPE se la classe è un tipo di valore; in caso contrario, ELEMENT_TYPE_CLASS.  
  
 Se la classe accetta parametri di tipo (ad esempio, `ArrayList<T>`), è possibile utilizzare `GetParameterizedType` per costruire un oggetto di tipo per un tipo istanziato come `ArrayList<int>`.  
  
## <a name="background-information"></a>Informazioni di base  
 Nelle versioni di .NET Framework 1.0 e 1.1, ogni tipo di metadati potrebbe essere mappata direttamente a un tipo di processo in esecuzione. Di conseguenza, un tipo di metadati e un tipo di runtime aveva una sola rappresentazione nel processo in esecuzione. Tuttavia, nei metadati su un tipo generico può essere mappato a molti creazioni di istanze diverse del tipo di processo in esecuzione. Ad esempio, il tipo di metadati `SortedList<K,V>` può eseguire il mapping a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`e così via. Di conseguenza, è necessario un modo per gestire la creazione di istanze di tipo.  
  
 .NET Framework versione 2.0 introduce il `ICorDebugType` interfaccia. Per un tipo generico, un `ICorDebugClass` o `ICorDebugClass2` rappresenta il tipo privo di istanze (`SortedList<K,V>`) e un `ICorDebugType` oggetto rappresenta i diversi tipi di istanziati. Dato un `ICorDebugClass` o `ICorDebugClass2` dell'oggetto, è possibile creare un `ICorDebugType` oggetto per ogni istanza creata chiamando il `ICorDebugClass2::GetParameterizedType` metodo. È inoltre possibile creare un `ICorDebugType` oggetto per un tipo semplice, ad esempio Int32, o un tipo non generico.  
  
 L'introduzione del `ICorDebugType` oggetto per rappresentare la nozione di in fase di esecuzione di un tipo ha un effetto in tutta l'API. Funzioni che accettavano in precedenza un `ICorDebugClass` o `ICorDebugClass2` oggetto o anche un `CorElementType` valore corrispondenti sono generalizzati per richiedere un `ICorDebugType` oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
