---
title: Metodo ICorProfilerInfo::SetILInstrumentedCodeMap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 127f6d76e85ed30f1407d16f8d81c93dd2941960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>Metodo ICorProfilerInfo::SetILInstrumentedCodeMap
Imposta una mappa del codice per la funzione specificata utilizzando le voci della mappa specificate Microsoft intermediate language (MSIL).  
  
> [!NOTE]
>  In .NET Framework versione 2.0, la chiamata `SetILInstrumentedCodeMap` su un `FunctionID` che rappresenta una funzione generica in un determinato dominio applicazione avrà effetto su tutte le istanze di tale funzione nel dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione per cui impostare la mappa del codice.  
  
 `fStartJit`  
 [in] Un valore booleano che indica se la chiamata al `SetILInstrumentedCodeMap` metodo è il primo di una particolare `FunctionID`. Impostare `fStartJit` a `true` nella prima chiamata a `SetILInstrumentedCodeMap` per un determinato `FunctionID`e a `false` successivamente.  
  
 `cILMapEntries`  
 [in] Il numero di elementi di `cILMapEntries` matrice.  
  
 `rgILMapEntries`  
 [in] Matrice di strutture COR_IL_MAP, ognuno dei quali specifica un offset MSIL.  
  
## <a name="remarks"></a>Note  
 Un profiler spesso inserisce istruzioni all'interno del codice sorgente di un metodo per instrumentare tale metodo (ad esempio, per inviare una notifica quando viene raggiunta una riga di origine specificato). `SetILInstrumentedCodeMap`consente a un profiler eseguire il mapping delle istruzioni MSIL originale nelle nuove posizioni. Un profiler può utilizzare il [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) metodo per ottenere l'offset MSIL originale per un determinato offset nativo.  
  
 Il debugger si presupporrà che ogni offset precedente fa riferimento a un offset all'interno del codice MSIL originale, non modificato MSIL e che ogni nuovo offset fa riferimento all'offset all'interno del codice instrumentato MSIL. La mappa deve essere ordinata in ordine crescente. Per l'esecuzione di istruzioni per il corretto funzionamento, seguire queste linee guida:  
  
-   Riordina il codice instrumentato MSIL.  
  
-   Non rimuovere il codice MSIL originale.  
  
-   Includere le voci per tutti i punti di sequenza dal file di database di (programma PDB) di programma nella mappa. La mappa non interpolare voci mancanti. In tal caso, si consideri la mappa seguente:  
  
     (vecchio, 0, 0 nuovo)  
  
     (5 vecchio, 10 nuovi)  
  
     (9 vecchio, 20 nuovo)  
  
    -   Verrà eseguito il mapping di un offset di 0, 1, 2, 3 o 4 precedente al nuovo offset 0.  
  
    -   Verrà eseguito il mapping di un offset di 5, 6, 7 o 8 precedente al nuovo offset 10.  
  
    -   Verrà eseguito il mapping di un offset di 9 o versione successiva precedente al nuovo offset 20.  
  
    -   Verrà eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.  
  
    -   Verrà eseguito il mapping di un nuovo offset pari a 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.  
  
    -   Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
