---
title: Metodo ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9f22f23835f01022d5d62596b2cf63425759193
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426063"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>Metodo ISymUnmanagedReader::GetSymAttribute
Ottiene un attributo personalizzato in base al relativo nome. Diversamente dagli attributi personalizzati di metadati, gli attributi personalizzati sono contenuti nell'archivio simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `parent`  
 [in] Il token di metadati per l'oggetto per cui è richiesto l'attributo.  
  
 `name`  
 [in] Puntatore alla variabile che indica l'attributo da recuperare.  
  
 `cBuffer`  
 [in] Dimensione della matrice `buffer`.  
  
 `pcBuffer`  
 [out] Puntatore a una variabile che riceve la lunghezza dei dati degli attributi.  
  
 `buffer`  
 [out] Puntatore a una variabile che riceve i dati dell'attributo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore...  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
