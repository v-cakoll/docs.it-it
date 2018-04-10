---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9082a05900330be27066b64f2ad0e99b87e04c61
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) di database, purché le informazioni sulla riga soddisfa i requisiti. Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe nella funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pIStream`  
 [in] Un puntatore a un [IStream](https://msdn.microsoft.com/library/aa380034.aspx) che contiene le informazioni sulla riga.  
  
 `pDeltaLines`  
 [in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.  
  
 `cDeltaLines`  
 [in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
