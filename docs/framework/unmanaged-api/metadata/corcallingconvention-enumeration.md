---
title: Enumerazione CorCallingConvention
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c0fbbb5f2c8f73cb6c76137263fa457840cdddc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corcallingconvention-enumeration"></a>Enumerazione CorCallingConvention
Contiene valori che descrivono i tipi di convenzioni di chiamata eseguite in codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Indica una convenzione di chiamata predefinita.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Indica che il metodo accetta un numero variabile di parametri.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Indica che la chiamata è per un campo.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Indica che la chiamata è per un metodo locale.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Indica che la chiamata è per una proprietà.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Indica che la chiamata non gestita.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Indica un'istanza di metodo generico.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Indica una chiamata di PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Viene descritto un valore a 4 bit non valido.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Indica che la convenzione di chiamata è descritta da ultimi quattro bit.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Indica che il primo bit descrive un `this` parametro.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Indica che un `this` è descritto in modo esplicito nella firma del parametro.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Indica una firma di metodo generico con un numero di argomenti di tipo esplicito. Questo precede un numero di parametri comuni.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
