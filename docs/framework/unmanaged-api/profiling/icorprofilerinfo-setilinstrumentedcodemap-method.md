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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc13dc1348a6d397c86b03976c86c3595f749cf6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480065"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>Metodo ICorProfilerInfo::SetILInstrumentedCodeMap
Imposta una mappa codici per la funzione specificata utilizzando voci della mappa specificate Microsoft intermediate language (MSIL).  
  
> [!NOTE]
>  In .NET Framework versione 2.0, la chiamata `SetILInstrumentedCodeMap` su un `FunctionID` che rappresenta una funzione generica in un determinato dominio dell'applicazione influirà su tutte le istanze della funzione nel dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui impostare la mappa del codice.  
  
 `fStartJit`  
 [in] Un valore booleano che indica se la chiamata per il `SetILInstrumentedCodeMap` metodo è il primo di una particolare `FunctionID`. Impostare `fStartJit` al `true` nella prima chiamata a `SetILInstrumentedCodeMap` per un determinato `FunctionID`e a `false` successivamente.  
  
 `cILMapEntries`  
 [in] Il numero di elementi nel `cILMapEntries` matrice.  
  
 `rgILMapEntries`  
 [in] Matrice di strutture COR_IL_MAP, ognuno dei quali specifica un offset MSIL.  
  
## <a name="remarks"></a>Note  
 Spesso, un profiler inserisce istruzioni all'interno del codice sorgente di un metodo per instrumentare tale metodo (ad esempio, per inviare una notifica quando viene raggiunta una riga di origine specificato). `SetILInstrumentedCodeMap` consente a un profiler eseguire il mapping di istruzioni MSIL originale nelle nuove posizioni. Un profiler può usare la [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) metodo per ottenere l'offset MSIL originale per un determinato offset nativi.  
  
 Il debugger presuppone che ogni offset precedente fa riferimento a un offset all'interno del codice MSIL originale, non modificato MSIL e che ogni nuovo offset fa riferimento all'offset all'interno del nuovo codice instrumentato MSIL. La mappa deve essere disposti in ordine crescente. Per l'esecuzione di istruzioni per il corretto funzionamento, seguire queste linee guida:  
  
-   Non riordinano le codice instrumentato MSIL.  
  
-   Non rimuovere il codice MSIL originale.  
  
-   Includere le voci per tutti i punti di sequenza dal file di database (PDB) di programma nella mappa. La mappa non esegue l'interpolazione voci mancanti. Pertanto, data la mappa seguente:  
  
     (0 precedente, 0 nuovi)  
  
     (5 precedenti, 10 nuovi)  
  
     (9 precedente, 20 nuovi)  
  
    -   Verrà eseguito il mapping di un offset 0, 1, 2, 3 o 4 precedente al nuovo offset 0.  
  
    -   Verrà eseguito il mapping di un offset precedente del 5, 6, 7 o 8 al nuovo offset 10.  
  
    -   Verrà eseguito il mapping di un offset precedente del 9 o versione successiva al nuovo offset 20.  
  
    -   Verrà eseguito il mapping di un nuovo offset 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.  
  
    -   Verrà eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.  
  
    -   Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
