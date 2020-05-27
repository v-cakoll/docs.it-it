---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 7c6adcbcfe64f63048078b4ccba6727a58531033
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008105"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyProps
Modifica la struttura dei metadati `Assembly` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pma`  
 in Token di metadati che specifica la `Assembly` struttura dei metadati da modificare.  
  
 `pbPublicKey`  
 in Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.  
  
 `cbPublicKey`  
 in Dimensioni in byte di `pbPublicKey` .  
  
 `ulHashAlgId`  
 in Identificatore dell'algoritmo hash utilizzato per eseguire l'hashing dei file di assembly.  
  
 `szName`  
 in Nome di testo leggibile dell'assembly.  
  
 `pMetaData`  
 in Puntatore a ASSEMBLYMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 in Combinazione bit per bit di valori [AssemblyFlags](assemblyflags-enumeration.md) che specificano diversi attributi dell'assembly.  
  
## <a name="remarks"></a>Commenti  
 Per creare una `Assembly` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
