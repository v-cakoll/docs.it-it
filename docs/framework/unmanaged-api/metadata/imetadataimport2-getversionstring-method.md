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
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490407"
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
 in Dimensione, in caratteri wide, della `pwzBuf` matrice.  
  
 `pccBufSize`  
 out Il numero di caratteri wide, incluso un carattere di terminazione null, restituito nella `pwzBuf` matrice.  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetVersionString` metodo ottiene la versione predefinita dell'ambito dei metadati corrente. Se l'ambito non è mai stato salvato, non sarà presente una versione predefinita e verrà restituita una stringa vuota.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
