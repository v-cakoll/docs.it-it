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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176175"
---
# <a name="corgenericparamattr-enumeration"></a>Enumerazione CorGenericParamAttr
Contiene valori che <xref:System.Type> descrivono i parametri per i tipi generici, utilizzati nelle chiamate a [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza dei parametri si applica solo ai parametri generici per interfacce e delegati.|  
|`gpNonVariant`|Indica l'assenza di varianza.|  
|`gpCovariant`|Indica la covarianza.|  
|`gpContravariant`|Indica la controvarianza.|  
|`gpSpecialConstraintMask`|È possibile applicare <xref:System.Type> vincoli speciali a qualsiasi parametro.|  
|`gpNoSpecialConstraint`|Indica che nessun vincolo <xref:System.Type> viene applicato al parametro.|  
|`gpReferenceTypeConstraint`|Indica che <xref:System.Type> il parametro deve essere un tipo di riferimento.|  
|`gpNotNullableValueTypeConstraint`|Indica che <xref:System.Type> il parametro deve essere un tipo di valore che non può essere un valore null.|  
|`gpDefaultConstructorConstraint`|Indica che <xref:System.Type> il parametro deve avere un costruttore pubblico predefinito che non accetta parametri.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr.h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
