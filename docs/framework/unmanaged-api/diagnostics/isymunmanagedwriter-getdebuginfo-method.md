---
title: Metodo ISymUnmanagedWriter::GetDebugInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1e9a2261ab5fd06e0514efdddf8a8e952a6e3d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426900"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Metodo ISymUnmanagedWriter::GetDebugInfo
Restituisce le informazioni necessarie per un compilatore per scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile. Il writer di simboli compila tutti i campi, ad eccezione di `TimeDateStamp` e `PointerToRawData`. (Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato).  
  
 Un compilatore deve chiamare questo metodo, creare il blob di dati per il file PE, impostare il `PointerToRawData` campo la IMAGE_DEBUG_DIRECTORY ai dati e scrivere la IMAGE_DEBUG_DIRECTORY file PE. Il compilatore deve inoltre impostare il `TimeDateStamp` campo deve essere uguale al `TimeDateStamp` del file PE in corso la generazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pIDD`  
 [in, out] Un puntatore a una IMAGE_DEBUG_DIRECTORY che verrà compilato il writer di simboli.  
  
 `cData`  
 [in] Oggetto `DWORD` che contiene la dimensione dei dati di debug.  
  
 `pcData`  
 [out] Un puntatore a un `DWORD` che riceve le dimensioni del buffer necessaria per contenere i dati di debug.  
  
 `data`  
 [out] Un puntatore a un buffer che è sufficientemente grande da contenere i dati per l'archivio dei simboli di debug.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
