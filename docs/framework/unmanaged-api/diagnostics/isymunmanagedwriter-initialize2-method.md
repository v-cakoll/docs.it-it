---
title: Metodo ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 869d7d36ac24bfeee5b2361dd569945ad77eaf7f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610067"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Metodo ISymUnmanagedWriter::Initialize2
Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug. Questo metodo consente inoltre di impostare il percorso finale del file del database di programma (PDB).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parametri  
 `emitter`  
 in Puntatore all'interfaccia di emissione dei metadati.  
  
 `tempfilename`  
 in Puntatore a un oggetto `WCHAR` che contiene il nome file in cui vengono scritti i simboli di debug. Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.  
  
 `pIStream`  
 in Se specificato, il writer di simboli emette i simboli nell'oggetto specificato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nel `filename` parametro. `pIStream` è facoltativo.  
  
 `fFullBuild`  
 [in] `true` Se si tratta di una ricompilazione completa; `false`se si tratta di una compilazione incrementale.  
  
 `finalfilename`  
 in Puntatore a un oggetto `WCHAR` che rappresenta la stringa di percorso della posizione finale del file PDB.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Metodo Initialize](isymunmanagedwriter-initialize-method.md)
