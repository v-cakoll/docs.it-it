---
title: Metodo ICorProfilerInfo::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: 99e473268fd0d5bb8ce120b97576277949b86508
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868997"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>Metodo ICorProfilerInfo::SetILInstrumentedCodeMap

Imposta una mappa codice per la funzione specificata utilizzando le voci della mappa MSIL (Microsoft Intermediate Language) specificate.

> [!NOTE]
> Nel .NET Framework versione 2,0, la chiamata di `SetILInstrumentedCodeMap` in un `FunctionID` che rappresenta una funzione generica in un particolare dominio applicazione influirà su tutte le istanze di tale funzione nel dominio applicazione.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>Parametri

`functionId`\
in ID della funzione per la quale impostare la mappa del codice.

`fStartJit`\
in Valore booleano che indica se la chiamata al metodo `SetILInstrumentedCodeMap` è la prima per un `FunctionID`specifico. Impostare `fStartJit` su `true` nella prima chiamata al `SetILInstrumentedCodeMap` per un determinato `FunctionID`e `false` successivamente.

`cILMapEntries`\
in Numero di elementi nella matrice `cILMapEntries`.

`rgILMapEntries`\
in Matrice di strutture di COR_IL_MAP, ognuna delle quali specifica un offset MSIL.

## <a name="remarks"></a>Note

Un profiler spesso inserisce istruzioni all'interno del codice sorgente di un metodo per instrumentare il metodo (ad esempio, per inviare una notifica quando viene raggiunta una determinata riga di codice sorgente). `SetILInstrumentedCodeMap` consente a un profiler di eseguire il mapping delle istruzioni MSIL originali ai nuovi percorsi. Un profiler può usare il metodo [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) per ottenere l'offset MSIL originale per un offset nativo specificato.

Il debugger presuppone che ogni offset precedente faccia riferimento a un offset MSIL all'interno del codice MSIL originale, non modificato e che ogni nuovo offset faccia riferimento all'offset MSIL all'interno del nuovo codice instrumentato. La mappa deve essere ordinata in ordine crescente. Per il corretto funzionamento, attenersi alle seguenti linee guida:

- Non riordinare il codice MSIL instrumentato.

- Non rimuovere il codice MSIL originale.

- Includere le voci per tutti i punti di sequenza dal file di database di programma (PDB) nella mappa. La mappa non esegue l'interpolazione delle voci mancanti. Quindi, data la mappa seguente:

  (0 vecchio, 0 nuovo)

  (5 anni, 10 nuovi)

  (9 anni, 20 nuovi)

  - Viene eseguito il mapping di un offset precedente di 0, 1, 2, 3 o 4 al nuovo offset 0.

  - Viene eseguito il mapping di un offset precedente di 5, 6, 7 o 8 al nuovo offset 10.

  - Verrà eseguito il mapping di un offset precedente di 9 o superiore al nuovo offset 20.

  - Viene eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 all'offset precedente 0.

  - Viene eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 alla precedente offset 5.

  - Verrà eseguito il mapping di un nuovo offset di 20 o superiore alla precedente offset 9.

In .NET Framework 3,5 e versioni precedenti, è necessario allocare la matrice di `rgILMapEntries` chiamando il metodo [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) . Poiché il runtime acquisisce la proprietà della memoria, il profiler non deve tentare di liberarlo.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
