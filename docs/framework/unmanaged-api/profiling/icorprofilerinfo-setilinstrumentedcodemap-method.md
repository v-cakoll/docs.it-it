---
title: Metodo ICorProfilerInfo::SetILInstrumentedCodeMap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 35c87b98a8e0c02ab6f4bca7a4f7a16ff6839c6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="fde18-102">Metodo ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="fde18-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="fde18-103">Imposta una mappa del codice per la funzione specificata utilizzando le voci della mappa specificate Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="fde18-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fde18-104">In .NET Framework versione 2.0, la chiamata `SetILInstrumentedCodeMap` su un `FunctionID` che rappresenta una funzione generica in un determinato dominio applicazione avrà effetto su tutte le istanze di tale funzione nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fde18-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde18-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fde18-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fde18-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fde18-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fde18-107">[in] L'ID della funzione per cui impostare la mappa del codice.</span><span class="sxs-lookup"><span data-stu-id="fde18-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="fde18-108">[in] Un valore booleano che indica se la chiamata al `SetILInstrumentedCodeMap` metodo è il primo di una particolare `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="fde18-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="fde18-109">Impostare `fStartJit` a `true` nella prima chiamata a `SetILInstrumentedCodeMap` per un determinato `FunctionID`e a `false` successivamente.</span><span class="sxs-lookup"><span data-stu-id="fde18-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="fde18-110">[in] Il numero di elementi di `cILMapEntries` matrice.</span><span class="sxs-lookup"><span data-stu-id="fde18-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="fde18-111">[in] Matrice di strutture COR_IL_MAP, ognuno dei quali specifica un offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="fde18-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fde18-112">Note</span><span class="sxs-lookup"><span data-stu-id="fde18-112">Remarks</span></span>  
 <span data-ttu-id="fde18-113">Un profiler spesso inserisce istruzioni all'interno del codice sorgente di un metodo per instrumentare tale metodo (ad esempio, per inviare una notifica quando viene raggiunta una riga di origine specificato).</span><span class="sxs-lookup"><span data-stu-id="fde18-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="fde18-114">`SetILInstrumentedCodeMap`consente a un profiler eseguire il mapping delle istruzioni MSIL originale nelle nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="fde18-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="fde18-115">Un profiler può utilizzare il [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) metodo per ottenere l'offset MSIL originale per un determinato offset nativo.</span><span class="sxs-lookup"><span data-stu-id="fde18-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="fde18-116">Il debugger si presupporrà che ogni offset precedente fa riferimento a un offset all'interno del codice MSIL originale, non modificato MSIL e che ogni nuovo offset fa riferimento all'offset all'interno del codice instrumentato MSIL.</span><span class="sxs-lookup"><span data-stu-id="fde18-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="fde18-117">La mappa deve essere ordinata in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="fde18-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="fde18-118">Per l'esecuzione di istruzioni per il corretto funzionamento, seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="fde18-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="fde18-119">Riordina il codice instrumentato MSIL.</span><span class="sxs-lookup"><span data-stu-id="fde18-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="fde18-120">Non rimuovere il codice MSIL originale.</span><span class="sxs-lookup"><span data-stu-id="fde18-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="fde18-121">Includere le voci per tutti i punti di sequenza dal file di database di (programma PDB) di programma nella mappa.</span><span class="sxs-lookup"><span data-stu-id="fde18-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="fde18-122">La mappa non interpolare voci mancanti.</span><span class="sxs-lookup"><span data-stu-id="fde18-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="fde18-123">In tal caso, si consideri la mappa seguente:</span><span class="sxs-lookup"><span data-stu-id="fde18-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="fde18-124">(vecchio, 0, 0 nuovo)</span><span class="sxs-lookup"><span data-stu-id="fde18-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="fde18-125">(5 vecchio, 10 nuovi)</span><span class="sxs-lookup"><span data-stu-id="fde18-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="fde18-126">(9 vecchio, 20 nuovo)</span><span class="sxs-lookup"><span data-stu-id="fde18-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="fde18-127">Verrà eseguito il mapping di un offset di 0, 1, 2, 3 o 4 precedente al nuovo offset 0.</span><span class="sxs-lookup"><span data-stu-id="fde18-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="fde18-128">Verrà eseguito il mapping di un offset di 5, 6, 7 o 8 precedente al nuovo offset 10.</span><span class="sxs-lookup"><span data-stu-id="fde18-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="fde18-129">Verrà eseguito il mapping di un offset di 9 o versione successiva precedente al nuovo offset 20.</span><span class="sxs-lookup"><span data-stu-id="fde18-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="fde18-130">Verrà eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.</span><span class="sxs-lookup"><span data-stu-id="fde18-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="fde18-131">Verrà eseguito il mapping di un nuovo offset pari a 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.</span><span class="sxs-lookup"><span data-stu-id="fde18-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="fde18-132">Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.</span><span class="sxs-lookup"><span data-stu-id="fde18-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde18-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fde18-133">Requirements</span></span>  
 <span data-ttu-id="fde18-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fde18-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde18-135">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fde18-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fde18-136">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fde18-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fde18-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde18-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde18-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fde18-138">See Also</span></span>  
 [<span data-ttu-id="fde18-139">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fde18-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
