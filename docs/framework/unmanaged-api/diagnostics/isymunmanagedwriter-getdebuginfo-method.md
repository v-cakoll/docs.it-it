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
ms.openlocfilehash: f8eb4cb6bad95295e10a72812fa8dbb0adfcc898
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614786"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>Metodo ISymUnmanagedWriter::GetDebugInfo
Restituisce le informazioni necessarie affinché un compilatore scriva la voce della directory di debug nell'intestazione del file eseguibile Portable (PE). Il writer di simboli compila tutti i campi ad eccezione di `TimeDateStamp` e `PointerToRawData` . Il compilatore è responsabile dell'impostazione di questi due campi in modo appropriato.  
  
 Un compilatore deve chiamare questo metodo, creare il BLOB di dati nel file PE, impostare il `PointerToRawData` campo nell'IMAGE_DEBUG_DIRECTORY in modo che punti ai dati emessi e scrivere la IMAGE_DEBUG_DIRECTORY nel file PE. Il compilatore deve inoltre impostare il `TimeDateStamp` campo in modo che corrisponda all'oggetto `TimeDateStamp` del file PE da generare.  
  
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
 in Oggetto `DWORD` che contiene le dimensioni dei dati di debug.  
  
 `pcData`  
 out Puntatore a un oggetto `DWORD` che riceve le dimensioni del buffer necessarie per contenere i dati di debug.  
  
 `data`  
 out Puntatore a un buffer sufficientemente grande da contenere i dati di debug per l'archivio dei simboli.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
