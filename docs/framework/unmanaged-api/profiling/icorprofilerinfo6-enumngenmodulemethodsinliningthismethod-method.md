---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948525"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod

Restituisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e inline un determinato metodo.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>Parametri

`inlinersModuleId`\
[in] L'identificatore di un modulo NGen.

`inlineeModuleId`\
[in] L'identificatore di un modulo che definisce `inlineeMethodId`. Per altre informazioni, vedere la sezione Osservazioni.

`inlineeMethodId`\
[in] L'identificatore di un metodo di implementazione inline. Per altre informazioni, vedere la sezione Osservazioni.

`incompleteData`\
[out] Un flag che indica se `ppEnum` contiene tutti i metodi l'incorporamento di un determinato metodo.  Per altre informazioni, vedere la sezione Osservazioni.

`ppEnum`\
[out] Un puntatore all'indirizzo di un enumeratore

## <a name="remarks"></a>Note

`inlineeModuleId` e `inlineeMethodId` insieme formano l'identificatore completo per il metodo che può essere impostato come inline. Si supponga ad esempio modulo `A` definisce un metodo `Simple.Add`:

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

e definisce il modulo B `Fancy.AddTwice`:

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Si supponga anche che `Fancy.AddTwice` inlines la chiamata a `SimpleAdd`. Un profiler può usare l'enumeratore per trovare tutti i metodi definiti nel modulo B che inline `Simple.Add`, e il risultato sarebbe enumerare `AddTwice`.  `inlineeModuleId` è l'identificatore del modulo `A`, e `inlineeMethodId` è l'identificatore di `Simple.Add(int a, int b)`.

Se `incompleteData` è true dopo la funzione termina, l'enumeratore non contiene tutti i metodi inline un determinato metodo. Questa situazione può verificarsi quando uno o più dipendenze dirette o indirette di inliners modulo non è stato ancora caricate. Se un profiler deve dati accurati, provare a ripetere in un secondo momento quando vengono caricati più moduli, preferibilmente ogni caricamento del modulo.

Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere usato per aggirare le limitazioni nell'incorporamento per ReJIT. ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi creare di nuovo codice appositamente in tempo reale. Ad esempio, è possibile modificare `Simple.Add` come indicato di seguito:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Tuttavia poiché `Fancy.AddTwice` ha già impostato come inline `Simple.Add`, continua ad avere lo stesso comportamento come in precedenza. Per aggirare questa limitazione, il chiamante dispone cercare tutti i metodi in tutti i moduli inline `Simple.Add` e usare `ICorProfilerInfo5::RequestRejit` in ognuno di questi metodi. Quando i metodi sono nuovamente compilati, hanno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo6](icorprofilerinfo6-interface.md)