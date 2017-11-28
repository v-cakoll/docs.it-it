---
title: Enumerazione CorFileMapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFileMapping
helpviewer_keywords: CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6736f154ef6b03c0bfe34d16a419955324316273
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corfilemapping-enumeration"></a>Enumerazione CorFileMapping
Contiene valori che descrivono il tipo di mapping del file restituito da una chiamata al [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`fmFlat`|Il file viene eseguito il mapping come file di dati. Vale a dire il `SEC_IMAGE` flag non è stato passato a Microsoft Win32 `CreateFileMapping` (funzione).|  
|`fmExecutableImage`|Il file viene eseguito il mapping per l'esecuzione, utilizzando il `LoadLibrary` funzione o `CreateFileMapping` utilizzabile con il `SEC_IMAGE` flag.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [GetFileMapping (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
