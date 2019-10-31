---
title: Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130381"
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
in Identificatore di un modulo che definisce `inlineeMethodId`. Per altre informazioni, vedere la sezione Osservazioni.

`inlineeMethodId`\
in Identificatore di un metodo inline. Per altre informazioni, vedere la sezione Osservazioni.

`incompleteData`\
out Flag che indica se `ppEnum` contiene tutti i metodi che incorporano un determinato metodo.  Per altre informazioni, vedere la sezione Osservazioni.

`ppEnum`\
out Puntatore all'indirizzo di un enumeratore

## <a name="remarks"></a>Note

`inlineeModuleId` e `inlineeMethodId` formano l'identificatore completo per il metodo che potrebbe essere inline. Si supponga, ad esempio, che il modulo `A` definisce un metodo `Simple.Add`:

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

e il modulo B definisce `Fancy.AddTwice`:

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Si supponga inoltre che `Fancy.AddTwice` inlineri la chiamata al `SimpleAdd`. Un profiler può utilizzare questo enumeratore per trovare tutti i metodi definiti nel modulo B che inline `Simple.Add`e il risultato enumera `AddTwice`.  `inlineeModuleId` è l'identificatore della `A`del modulo e `inlineeMethodId` è l'identificatore del `Simple.Add(int a, int b)`.

Se `incompleteData` è true dopo la restituzione della funzione, l'enumeratore non contiene tutti i metodi che incorporano un determinato metodo. Questo problema può verificarsi quando una o più dipendenze dirette o indirette del modulo Inliners non sono ancora state caricate. Se un profiler richiede dati accurati, è consigliabile riprovare più tardi quando vengono caricati più moduli, preferibilmente a ogni caricamento del modulo.

Il metodo `EnumNgenModuleMethodsInliningThisMethod` può essere usato per aggirare le limitazioni sull'incorporamento di ReJIT. ReJIT consente a un profiler di modificare l'implementazione di un metodo e quindi di crearne il nuovo codice in tempo reale. Ad esempio, è possibile modificare `Simple.Add` come indicato di seguito:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Tuttavia, poiché `Fancy.AddTwice` è già stato inline `Simple.Add`, continua a avere lo stesso comportamento di prima. Per ovviare a questa limitazione, il chiamante deve cercare tutti i metodi in tutti i moduli che inline `Simple.Add` e utilizzare `ICorProfilerInfo5::RequestRejit` su ognuno di questi metodi. Quando i metodi vengono nuovamente compilati, avranno il nuovo comportamento di `Simple.Add` al posto del comportamento precedente.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo6](icorprofilerinfo6-interface.md)
