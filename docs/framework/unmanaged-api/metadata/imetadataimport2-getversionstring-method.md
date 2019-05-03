---
title: Metodo IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a01b4203145f6ffee4e3a11a3526f0b83e3dc741
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042523"
---
# <a name="imetadataimport2getversionstring-method"></a>Metodo IMetaDataImport2::GetVersionString
Ottiene il numero di versione del runtime che è stato usato per compilare l'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuf`  
 [out] Una matrice per archiviare la stringa che specifica la versione.  
  
 `ccBufSize`  
 [in] Le dimensioni, in caratteri "wide", del `pwzBuf` matrice.  
  
 `pccBufSize`  
 [out] Il numero di caratteri "wide", incluso un carattere di terminazione null, restituito nel `pwzBuf` matrice.  
  
## <a name="remarks"></a>Note  
 Il `GetVersionString` metodo ottiene la versione compilata dell'ambito dei metadati corrente. Se l'ambito non è mai stato salvato, non disporrà di una versione e verrà restituita una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
