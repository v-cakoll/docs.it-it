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
ms.openlocfilehash: 2b901a3dac499f1ce3f843c59122dd8fd5022147
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427954"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Metodo ISymUnmanagedWriter::GetDebugInfo
Restituisce le informazioni necessarie affinché un compilatore scriva la voce della directory di debug nell'intestazione del file eseguibile Portable (PE). Il writer di simboli compila tutti i campi ad eccezione di `TimeDateStamp` e `PointerToRawData`. Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato.  
  
 Un compilatore deve chiamare questo metodo, creare il BLOB di dati nel file PE, impostare il campo `PointerToRawData` nel IMAGE_DEBUG_DIRECTORY in modo che punti ai dati emessi e scrivere il IMAGE_DEBUG_DIRECTORY nel file PE. Il compilatore deve inoltre impostare il campo `TimeDateStamp` in modo che corrisponda al `TimeDateStamp` del file PE da generare.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `pIDD`  
 [in, out] Puntatore a un IMAGE_DEBUG_DIRECTORY che il writer di simboli compilerà.  
  
 `cData`  
 in `DWORD` che contiene le dimensioni dei dati di debug.  
  
 `pcData`  
 out Puntatore a un `DWORD` che riceve le dimensioni del buffer necessarie per contenere i dati di debug.  
  
 `data`  
 out Puntatore a un buffer sufficientemente grande da contenere i dati di debug per l'archivio dei simboli.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
