---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: fb381a872cbeb787da0c6920f2cdeef434fb33ea
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008092"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
Modifica la struttura dei metadati `AssemblyRef` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ar`  
 in Token di metadati che specifica la `AssemblyRef` struttura dei metadati da modificare.  
  
 `pbPublicKeyOrToken`  
 in Chiave pubblica del server di pubblicazione dell'assembly a cui si fa riferimento.  
  
 `cbPublicKeyOrToken`  
 in Dimensioni in byte di `pbPublicKeyOrToken` .  
  
 `szName`  
 in Nome di testo leggibile dell'assembly.  
  
 `pMetaData`  
 in Puntatore a un'istanza di ASSEMBLYMETADATA che contiene le informazioni relative alla versione, alla piattaforma e alle impostazioni locali per l'assembly.  
  
 `pbHashValue`  
 in Puntatore ai dati hash associati all'assembly.  
  
 `cbHashValue`  
 in Dimensioni in byte di `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 in Combinazione bit per bit di valori [AssemblyRefFlags](assemblyrefflags-enumeration.md) che specificano gli attributi dell'assembly a cui si fa riferimento.  
  
## <a name="remarks"></a>Commenti  
 Per creare una `AssemblyRef` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efineassemblyref](imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
