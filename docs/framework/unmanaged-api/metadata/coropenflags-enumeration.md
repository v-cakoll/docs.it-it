---
title: Enumerazione CorOpenFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39645de71913baeaa39524e1cae081de9cac3442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="coropenflags-enumeration"></a>Enumerazione CorOpenFlags
Contiene valori di flag che controllano il comportamento dei metadati all'apertura di file manifesto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ofRead`|Indica che il file deve essere aperto in sola lettura.|  
|`ofWrite`|Indica che il file deve essere aperto in scrittura.<br /><br /> Se si usa il flag `ofWrite` quando si apre un file con estensione winmd, è anche necessario passare il flag `ofNoTransform`.|  
|`ofReadWriteMask`|Maschera per la lettura e la scrittura.|  
|`ofCopyMemory`|Indica che il file deve essere letto in memoria. I metadati devono mantenere la propria copia.|  
|`ofCacheImage`|Obsoleto. Questo flag viene ignorato.|  
|`ofManifestMetadata`|Obsoleto. Questo flag viene ignorato.|  
|`ofReadOnly`|Indica che il file deve essere aperto in lettura e che una chiamata a `QueryInterface` per un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) non può essere impostato.|  
|`ofTakeOwnership`|Indica che la memoria allocata tramite una chiamata a [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) e verrà liberata dai metadati.|  
|`ofNoTypeLib`|Obsoleta. Questo flag viene ignorato.|  
|`ofNoTransform`|Indica che le trasformazioni automatiche dei file con estensione winmd devono essere disabilitate. In altre parole, la proiezione di un tipo di Windows Runtime in un tipo di .NET Framework deve essere disabilitata. Per ulteriori informazioni, vedere [sottostante parte integrante di Windows Runtime e .NET](http://msdn.microsoft.com/magazine/jj651569.aspx).|  
|`ofReserved1`|Riservato per uso interno.|  
|`ofReserved2`|Riservato per uso interno.|  
|`ofReserved`|Riservato per uso interno.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
