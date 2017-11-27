---
title: Metodo IMetaDataDispenser::DefineScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.DefineScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 964e6df1b6aba7ca85b627cf19c38f5df600b6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserdefinescope-method"></a>Metodo IMetaDataDispenser::DefineScope
Crea una nuova area in memoria in cui è possibile creare nuovi metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `rclsid`  
 [in] Il CLSID della versione di strutture di metadati da creare. Questo valore deve essere CLSID_CorMetaDataRuntime per .NET Framework versione 2.0.  
  
 `dwCreateFlags`  
 [in] Flag che specificano le opzioni. Questo valore deve essere zero per .NET Framework 2.0.  
  
 `riid`  
 [in] L'IID dell'interfaccia di metadati desiderati da restituire. il chiamante utilizzerà l'interfaccia per creare i nuovi metadati.  
  
 Il valore di `riid` deve specificare una delle interfacce di "generazione". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit e IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [out] Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Note  
 `DefineScope`Crea un set di tabelle di metadati in memoria, genera un GUID (identificatore di versione del modulo o MVID) per i metadati e viene creata una voce nella tabella dei moduli per l'unità di compilazione generata.  
  
 È possibile collegare gli attributi per l'ambito dei metadati nel suo complesso usando il [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) metodo, come appropriato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataDispenser (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataDispenserEx (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
