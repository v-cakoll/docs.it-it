---
title: Metodo ISymUnmanagedReader2::GetSymAttributePreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 4009f8988c90ed090c0cc3d86164af347055722f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446424"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>Metodo ISymUnmanagedReader2::GetSymAttributePreRemap
Ottiene un attributo personalizzato in base al nome. Diversamente dagli attributi personalizzati dei metadati, questi attributi vengono conservati nell'archivio dei simboli.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `parent`  
 in Token di metadati dell'elemento padre.  
  
 `name`  
 in Puntatore a un `WCHAR` che contiene il nome.  
  
 `cBuffer`  
 in `ULONG32` che indica le dimensioni della matrice di `buffer`.  
  
 `pcBuffer`  
 out Puntatore a un `ULONG32` che riceve le dimensioni del buffer necessarie per contenere i byte dell'attributo.  
  
 `buffer`  
 out Puntatore al buffer che riceve i byte dell'attributo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
