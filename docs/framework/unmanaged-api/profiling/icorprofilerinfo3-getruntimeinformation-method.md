---
title: Metodo ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: b8e503af11fa1d02aac2ec83edde0ffbd562d8e5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496399"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Metodo ICorProfilerInfo3::GetRuntimeInformation
Fornisce informazioni sulla versione per il Common Language Runtime (CLR) sottofilato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClrInstanceId`  
 out ID rappresentativo di un'istanza CLR in esecuzione in un processo. Si tratta dello stesso oggetto `ClrInstanceID` che segnala l'evento di avvio di Event Tracing for Windows (ETW).  
  
 `pRuntimeType`  
 out Tipo di Runtime. Questo parametro restituisce `COR_PRF_DESKTOP_CLR` per la versione desktop di CLR o `COR_PRF_CORE_CLR` per la versione principale di CLR utilizzata in Silverlight.  
  
 `pMajorVersion`  
 out Numero di versione principale di CLR.  
  
 `pMinorVersion`  
 out Numero di versione secondario di CLR.  
  
 `pBuildVersion`  
 out Numero di versione della build di CLR.  
  
 `pQFEVersion`  
 out Numero di versione di CLR associato a un aggiornamento software.  
  
 `cchVersionString`  
 in Lunghezza, in caratteri, del buffer `szVersionString` a cui punta.  
  
 `pcchVersionString`  
 out Lunghezza, in caratteri, di `szVersionString` .  
  
 `szVersionString`  
 out Stringa della versione CLR.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile passare null per qualsiasi parametro. Tuttavia, `pcchVersionString` non può essere null a meno che `szVersionString` anche non sia null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
