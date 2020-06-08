---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 8ed3f305deceacb976aeff994db1588f9e1ce1fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495528"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod

Restituisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e incorporano un metodo specificato.

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
in Identificatore di un modulo NGen.

`inlineeModuleId`\
in Identificatore di un modulo che definisce `inlineeMethodId` . Per ulteriori informazioni, vedere le sezione Note.

`inlineeMethodId`\
in Identificatore di un metodo inline. Per ulteriori informazioni, vedere le sezione Note.

`incompleteData`\
out Flag che indica se `ppEnum` contiene tutti i metodi che incorporano un determinato metodo.  Per ulteriori informazioni, vedere le sezione Note.

`ppEnum`\
out Puntatore all'indirizzo di un enumeratore

## <a name="remarks"></a>Osservazioni

`inlineeModuleId``inlineeMethodId`insieme formano l'identificatore completo per il metodo che potrebbe essere inline. Si supponga, ad esempio, che il modulo definisca `A` un metodo `Simple.Add` :

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

e il modulo B definisce `Fancy.AddTwice` :

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Si supponga inoltre che `Fancy.AddTwice` inline la chiamata a `SimpleAdd` . Un profiler può utilizzare questo enumeratore per trovare tutti i metodi definiti nel modulo B che inline `Simple.Add` e il risultato verrebbe enumerato `AddTwice` .  `inlineeModuleId`è l'identificatore del modulo `A` e `inlineeMethodId` è l'identificatore di `Simple.Add(int a, int b)` .

Se `incompleteData` è true dopo la restituzione della funzione, l'enumeratore non contiene tutti i metodi che incorporano un determinato metodo. Questo problema può verificarsi quando una o più dipendenze dirette o indirette del modulo Inliners non sono ancora state caricate. Se un profiler richiede dati accurati, è consigliabile riprovare più tardi quando vengono caricati più moduli, preferibilmente a ogni caricamento del modulo.

Il `EnumNgenModuleMethodsInliningThisMethod` metodo può essere usato per aggirare le limitazioni sull'incorporamento di ReJIT. ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi di crearne il nuovo codice in tempo reale. Ad esempio, è possibile modificare `Simple.Add` come segue:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Tuttavia `Fancy.AddTwice` , poiché è già stato inline `Simple.Add` , continua a avere lo stesso comportamento che precede. Per ovviare a questa limitazione, il chiamante deve eseguire la ricerca di tutti i metodi in tutti i moduli che inline `Simple.Add` e utilizzano `ICorProfilerInfo5::RequestRejit` su ognuno di questi metodi. Quando i metodi vengono nuovamente compilati, avranno il nuovo comportamento di `Simple.Add` anziché il comportamento precedente.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo6](icorprofilerinfo6-interface.md)
