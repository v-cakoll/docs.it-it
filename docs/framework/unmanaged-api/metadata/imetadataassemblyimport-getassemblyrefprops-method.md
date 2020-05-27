---
title: Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 2858e924ab6effe192955ce53dad9d333d2d244d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009067"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdar`  
 in `mdAssemblyRef`Token di metadati che rappresenta il riferimento all'assembly per il quale ottenere le proprietà.  
  
 `ppbPublicKeyOrToken`  
 out Puntatore alla chiave pubblica o al token di metadati.  
  
 `pcbPublicKeyOrToken`  
 out Numero di byte nella chiave pubblica o nel token restituito.  
  
 `szName`  
 out Nome semplice dell'assembly.  
  
 `cchName`  
 in Dimensione, in caratteri wide, di `szName` .  
  
 `pchName`  
 out Puntatore al numero di caratteri wide effettivamente restituiti in `szName` .  
  
 `pMetaData`  
 out Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `ppbHashValue`  
 out Puntatore al valore hash. Si tratta dell'hash, che usa l'algoritmo SHA-1, della `PublicKey` proprietà dell'assembly a cui si fa riferimento, a meno che non sia impostato il flag arfFullOriginator dell'enumerazione [AssemblyRefFlags](assemblyrefflags-enumeration.md) .  
  
 `pcbHashValue`  
 out Numero di caratteri wide nel valore hash restituito.  
  
 `pdwAssemblyRefFlags`  
 out Puntatore ai flag che descrivono i metadati applicati a un assembly. Il valore dei flag è una combinazione di uno o più valori [CorAssemblyFlags](corassemblyflags-enumeration.md) .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce S_OK se ha esito positivo; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione Winerror. h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
