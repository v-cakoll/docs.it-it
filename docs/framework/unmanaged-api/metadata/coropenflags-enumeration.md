---
title: Enumerazione CorOpenFlags
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436500"
---
# <a name="coropenflags-enumeration"></a>Enumerazione CorOpenFlags
Contiene valori di flag che controllano il comportamento dei metadati all'apertura di file manifesto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ofRead`|Indica che il file deve essere aperto in sola lettura.|  
|`ofWrite`|Indica che il file deve essere aperto in scrittura.<br /><br /> Se si usa il flag `ofWrite` quando si apre un file con estensione winmd, è anche necessario passare il flag `ofNoTransform`.|  
|`ofReadWriteMask`|Maschera per la lettura e la scrittura.|  
|`ofCopyMemory`|Indica che il file deve essere letto in memoria. I metadati devono mantenere la propria copia.|  
|`ofCacheImage`|Obsoleto. Questo flag viene ignorato.|  
|`ofManifestMetadata`|Obsoleto. Questo flag viene ignorato.|  
|`ofReadOnly`|Indica che il file deve essere aperto per la lettura e che non è possibile effettuare una chiamata a `QueryInterface` per un oggetto [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) .|  
|`ofTakeOwnership`|Indica che la memoria è stata allocata utilizzando una chiamata a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) e verrà liberata dai metadati.|  
|`ofNoTypeLib`|Obsoleto. Questo flag viene ignorato.|  
|`ofNoTransform`|Indica che le trasformazioni automatiche dei file con estensione winmd devono essere disabilitate. In altre parole, la proiezione di un tipo di Windows Runtime in un tipo di .NET Framework deve essere disabilitata. Per ulteriori informazioni, vedere [Windows Runtime e CLR-sotto la cappa con .NET e il Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Riservato a un uso interno.|  
|`ofReserved2`|Riservato a un uso interno.|  
|`ofReserved`|Riservato a un uso interno.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
