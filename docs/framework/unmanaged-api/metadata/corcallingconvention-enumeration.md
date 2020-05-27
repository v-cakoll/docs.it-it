---
title: Enumerazione CorCallingConvention
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: 310319e8fefe80017c58706e2beaee5eb1e78422
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007906"
---
# <a name="corcallingconvention-enumeration"></a>Enumerazione CorCallingConvention
Contiene valori che descrivono i tipi di convenzioni per le chiamate effettuate in codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Indica che la chiamata è a un campo.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Indica che la chiamata è a un metodo locale.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Indica che la chiamata è a una proprietà.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Indica che la chiamata non è gestita.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Indica una creazione di un'istanza di metodo generica.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Indica una chiamata PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Descrive un valore a 4 bit non valido.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Indica che la convenzione di chiamata è descritta dai quattro bit inferiori.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Indica che il bit superiore descrive un `this` parametro.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Indica che un `this` parametro viene descritto in modo esplicito nella firma.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Indica una firma del metodo generico con un numero esplicito di argomenti di tipo. Questo precede un numero di parametri normali.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
