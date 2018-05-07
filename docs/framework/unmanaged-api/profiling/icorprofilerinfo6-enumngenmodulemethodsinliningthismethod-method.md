---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
[Supportato in .NET Framework 4.6 e versioni successive]  
  
 Restituisce un enumeratore per tutti i metodi definiti in un modulo NGen specificato e un determinato metodo inline.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `inlinersModuleId`  
 [in] L'identificatore di un modulo NGen.  
  
 `inlineeModuleId`  
 [in] L'identificatore di un modulo che definisce `inlineeMethodId`. Per altre informazioni, vedere la sezione Osservazioni.  
  
 `inlineeMethodId`  
 [in] L'identificatore di un metodo inline. Per altre informazioni, vedere la sezione Osservazioni.  
  
 `incompleteData`  
 [out] Un flag che indica se `ppEnum` contiene tutti i metodi di incorporamento di un metodo specificato.  Per altre informazioni, vedere la sezione Osservazioni.  
  
 `ppEnum`  
 [out] Un puntatore all'indirizzo di un enumeratore  
  
## <a name="remarks"></a>Note  
 `inlineeModuleId` e `inlineeMethodId` insieme formano l'identificatore completo per il metodo che potrebbe essere impostati come inline. Si supponga ad esempio modulo `A` definisce un metodo `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 modulo Bdefines e `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Si supponga inoltre che `Fancy.AddTwice` incorpora la chiamata a `SimpleAdd`. Un profiler potrebbe utilizzare l'enumeratore per trovare tutti i metodi definiti nel modulo B quali inline `Simple.Add`, e il risultato sarebbe enumerare `AddTwice`.  `inlineeModuleId` è l'identificatore del modulo `A`, e `inlineeeMethodId` è l'identificatore di `Simple.Add(int a, int b)`.  
  
 Se `incompleteData` è true, dopo la funzione restituisce un risultato, l'enumeratore non contiene tutti i metodi inline un metodo specificato. Questa situazione può verificarsi quando uno o più dipendenze dirette o indirette di inliners modulo non è stato ancora caricate. Se un profiler dati accurati, deve riprovare in seguito quando vengono caricati altri moduli, preferibilmente in ogni caricamento del modulo.  
  
 Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere utilizzato per aggirare le limitazioni in inline per ReJIT. ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi creare di nuovo codice per tale in tempo reale. Ad esempio, è possibile modificare `Simple.Add` come indicato di seguito:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Tuttavia poiché `Fancy.AddTwice` ha già resa inline `Simple.Add`, continua ad avere lo stesso comportamento come in precedenza. Per aggirare questa limitazione, il chiamante dispone cercare tutti i metodi in tutti i moduli che inline `Simple.Add` e utilizzare `ICorProfilerInfo5::RequestRejit` in ognuno di questi metodi. Quando i metodi sono ricompilati, avranno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
