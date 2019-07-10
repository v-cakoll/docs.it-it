---
title: Metodo IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1763f9341af2d90cf465cb554bf7f282a4d92058
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777804"
---
# <a name="imetadatadispenserdefinescope-method"></a>Metodo IMetaDataDispenser::DefineScope
Crea una nuova area in memoria in cui è possibile creare nuovi metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `rclsid`  
 [in] Il CLSID della versione di strutture di metadati da creare. Questo valore deve essere CLSID_CorMetaDataRuntime per .NET Framework versione 2.0.  
  
 `dwCreateFlags`  
 [in] Flag che specificano le opzioni. Questo valore deve essere zero per .NET Framework 2.0.  
  
 `riid`  
 [in] IID dell'interfaccia di metadati desiderati da restituire. il chiamante userà l'interfaccia per creare i nuovi metadati.  
  
 Il valore di `riid` deve specificare una delle interfacce "Crea". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Il puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 `DefineScope` Crea un set di tabelle di metadati in memoria, genera un GUID (identificatore della versione del modulo o MVID) per i metadati e crea una voce nella tabella dei moduli per l'unità di compilazione che venga generato.  
  
 È possibile collegare gli attributi per l'ambito dei metadati nel suo complesso tramite il [SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) oppure [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) metodo, come appropriato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
