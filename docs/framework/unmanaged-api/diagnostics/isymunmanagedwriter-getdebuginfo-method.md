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
ms.openlocfilehash: 87dd256bfe8a067ad798bff77a172b936f2d6aab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649934"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Metodo ISymUnmanagedWriter::GetDebugInfo
Restituisce le informazioni necessarie per un compilatore scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile. Compila tutti i campi eccetto per il writer di simboli `TimeDateStamp` e `PointerToRawData`. (Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato).  
  
 Un compilatore debba chiamare questo metodo, creare il blob di dati per il file PE, impostare il `PointerToRawData` campo la IMAGE_DEBUG_DIRECTORY per puntare ai dati e scrivere il IMAGE_DEBUG_DIRECTORY nel file PE. Il compilatore è necessario impostare anche il `TimeDateStamp` campo deve essere uguale al `TimeDateStamp` del file PE generato.  
  
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
 [in, out] Un puntatore a una IMAGE_DEBUG_DIRECTORY che compilerà il writer di simboli.  
  
 `cData`  
 [in] Oggetto `DWORD` che contiene la dimensione dei dati di debug.  
  
 `pcData`  
 [out] Un puntatore a un `DWORD` che riceve le dimensioni del buffer necessaria per contenere i dati di debug.  
  
 `data`  
 [out] Un puntatore a un buffer che è sufficientemente grande da contenere i dati di debug per l'archivio dei simboli.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
