---
title: Metodo IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 17c91200730431c4c6e230b8c1561ce7c4863868
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008183"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Metodo IMetaDataAssemblyEmit::DefineAssembly
Crea una `Assembly` struttura contenente i metadati per l'assembly specificato e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKey`  
 in Chiave pubblica che identifica il server di pubblicazione dell'assembly o NULL se l'assembly non ha un nome sicuro.  
  
 `cbPublicKey`  
 in Dimensioni in byte di `pbPublicKey` .  
  
 `uHashAlgId`  
 in Identificatore dell'algoritmo hash da usare per crittografare i file nell'assembly o NULL per specificare l'algoritmo SHA-1.  
  
 `szName`  
 in Nome di testo leggibile dell'assembly. Questo valore non deve superare i 1024 caratteri.  
  
 `pMetaData`  
 in Puntatore a un'istanza di ASSEMBLYMETADATA che contiene le informazioni relative alla versione, alla piattaforma e alle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 in Combinazione di valori [CorAssemblyFlags](corassemblyflags-enumeration.md) che descrivono le funzionalità dell'assembly.  
  
 `pmda`  
 out Puntatore al token di metadati.  
  
## <a name="remarks"></a>Commenti  
 `Assembly`All'interno di un manifesto è possibile definire una sola struttura di metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
