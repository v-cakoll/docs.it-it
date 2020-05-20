---
title: Metodo ISymUnmanagedReader::ReplaceSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: db2137146ded5200e05bbf88e23ae599f3eb7dec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615449"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>Metodo ISymUnmanagedReader::ReplaceSymbolStore
Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta. Questo metodo è simile al metodo [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) , ad eccezione del fatto che il delta specificato funge da sostituzione completa anziché da un aggiornamento.  
  
> [!NOTE]
> È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi. Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file. Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati del <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parametri  
 `filename`  
 in Nome del file contenente l'archivio dei simboli.  
  
 `pIStream`  
 in Flusso di file, usato come alternativa al `filename` parametro.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)
