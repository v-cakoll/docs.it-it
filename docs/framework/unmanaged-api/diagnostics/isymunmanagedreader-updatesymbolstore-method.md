---
title: Metodo ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: ccc787aa1c820a486d9a513055c9c9834b90bd1a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615436"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>Metodo ISymUnmanagedReader::UpdateSymbolStore
Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta. Questo metodo viene usato negli scenari di modifica e continuazione per aggiornare l'archivio simboli in modo che corrisponda ai Delta al file eseguibile portabile originale (PE).  
  
> [!NOTE]
> È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi. Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file. Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati del <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parametri  
 `filename`  
 in Nome del file che contiene l'archivio dei simboli.  
  
 `pIStream`  
 in Flusso di file, usato come alternativa al `filename` parametro.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](isymunmanagedreader-interface.md)
