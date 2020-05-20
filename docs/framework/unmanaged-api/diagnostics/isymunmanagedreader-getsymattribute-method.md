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
ms.openlocfilehash: b7e2814e56765037b69c6ef7ca0ba610dd7d3c95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614929"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>Metodo ISymUnmanagedReader::GetSymAttribute
Ottiene un attributo personalizzato in base al nome. Diversamente dagli attributi personalizzati dei metadati, questi attributi personalizzati vengono conservati nell'archivio dei simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `parent`  
 in Token di metadati per l'oggetto per il quale viene richiesto l'attributo.  
  
 `name`  
 in Puntatore alla variabile che indica l'attributo da recuperare.  
  
 `cBuffer`  
 [in] Dimensione della matrice `buffer`.  
  
 `pcBuffer`  
 out Puntatore alla variabile che riceve la lunghezza dei dati dell'attributo.  
  
 `buffer`  
 out Puntatore alla variabile che riceve i dati dell'attributo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)
