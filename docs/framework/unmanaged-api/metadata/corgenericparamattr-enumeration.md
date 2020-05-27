---
title: Enumerazione CorGenericParamAttr
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: ea84b742c901ba58a3bb730f1f5033a0d90610ce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007377"
---
# <a name="corgenericparamattr-enumeration"></a>Enumerazione CorGenericParamAttr
Contiene valori che descrivono i <xref:System.Type> parametri per i tipi generici, come usato nelle chiamate a [IMetaDataEmit2::D efinegenericparam](imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza dei parametri si applica solo ai parametri generici per interfacce e delegati.|  
|`gpNonVariant`|Indica l'assenza di varianza.|  
|`gpCovariant`|Indica la covarianza.|  
|`gpContravariant`|Indica la controvarianza.|  
|`gpSpecialConstraintMask`|I vincoli speciali possono essere applicati a qualsiasi <xref:System.Type> parametro.|  
|`gpNoSpecialConstraint`|Indica che non viene applicato alcun vincolo al <xref:System.Type> parametro.|  
|`gpReferenceTypeConstraint`|Indica che il <xref:System.Type> parametro deve essere un tipo riferimento.|  
|`gpNotNullableValueTypeConstraint`|Indica che il <xref:System.Type> parametro deve essere un tipo di valore che non può essere un valore null.|  
|`gpDefaultConstructorConstraint`|Indica che il <xref:System.Type> parametro deve disporre di un costruttore pubblico predefinito che non accetta parametri.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
