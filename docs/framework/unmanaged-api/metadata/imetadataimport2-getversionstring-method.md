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
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445219"
---
# <a name="imetadataimport2getversionstring-method"></a>Metodo IMetaDataImport2::GetVersionString
Ottiene il numero di versione del runtime utilizzato per compilare l'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuf`  
 out Una matrice in cui archiviare la stringa che specifica la versione.  
  
 `ccBufSize`  
 in Dimensione, in caratteri wide, della matrice `pwzBuf`.  
  
 `pccBufSize`  
 out Il numero di caratteri wide, incluso un carattere di terminazione null, restituito nella matrice `pwzBuf`.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo `GetVersionString` ottiene la versione predefinita dell'ambito dei metadati corrente. Se l'ambito non è mai stato salvato, non sarà presente una versione predefinita e verrà restituita una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
