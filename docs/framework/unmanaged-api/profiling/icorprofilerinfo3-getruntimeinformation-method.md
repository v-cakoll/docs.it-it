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
ms.openlocfilehash: e3d167be9a4091ae57a3283424186142e90ca7a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868551"
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
 out ID rappresentativo di un'istanza CLR in esecuzione in un processo. Si tratta dello stesso `ClrInstanceID` che l'evento di avvio di Event Tracing for Windows (ETW).  
  
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
 in Lunghezza, in caratteri, del buffer a cui punta il `szVersionString`.  
  
 `pcchVersionString`  
 out Lunghezza, in caratteri, del `szVersionString`.  
  
 `szVersionString`  
 out Stringa della versione CLR.  
  
## <a name="remarks"></a>Note  
 È possibile passare null per qualsiasi parametro. Tuttavia, `pcchVersionString` non può essere null a meno che anche `szVersionString` non sia null.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
