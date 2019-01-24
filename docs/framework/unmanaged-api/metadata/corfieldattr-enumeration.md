---
title: Enumerazione CorFieldAttr
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b07388b7f7385e93a6ca891e8ea98a2ce69763c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576015"
---
# <a name="corfieldattr-enumeration"></a>Enumerazione CorFieldAttr
Contiene valori che descrivono i metadati relativi a un campo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`fdFieldAccessMask`|Specifica le informazioni sull'accessibilità.|  
|`fdPrivateScope`|Specifica che il campo non può far riferimento.|  
|`fdPrivate`|Specifica che il campo è accessibile solo dal relativo tipo padre.|  
|`fdFamANDAssem`|Specifica che il campo è accessibile dalle classi derivate nel relativo assembly.|  
|`fdAssembly`|Specifica che il campo è accessibile da tutti i tipi nell'assembly.|  
|`fdFamily`|Specifica che il campo è accessibile solo dal relativo tipo e le classi derivate.|  
|`fdFamORAssem`|Specifica che il campo è accessibile dalle classi derivate e da tutti i tipi nell'assembly.|  
|`fdPublic`|Specifica che il campo è accessibile da tutti i tipi con visibilità dell'ambito.|  
|`fdStatic`|Specifica che il campo è un membro del suo tipo anziché un membro di istanza.|  
|`fdInitOnly`|Specifica che il campo non può essere modificato dopo l'inizializzazione.|  
|`fdLiteral`|Specifica che il valore del campo è una costante in fase di compilazione.|  
|`fdNotSerialized`|Specifica che il campo non è serializzato quando il relativo tipo viene eseguita in modalità remota.|  
|`fdSpecialName`|Specifica che il campo è speciale e che il relativo nome viene descritto come.|  
|`fdPinvokeImpl`|Specifica che l'implementazione del campo è inoltrata tramite PInvoke.|  
|`fdReservedMask`|Riservato per uso interno da common language runtime.|  
|`fdRTSpecialName`|Specifica che i metadati di common language runtime le API interne devono verificare la codifica del nome.|  
|`fdHasFieldMarshal`|Specifica che il campo contiene informazioni di marshalling.|  
|`fdHasDefault`|Specifica che il campo ha un valore predefinito.|  
|`fdHasFieldRVA`|Specifica che il campo ha un indirizzo virtuale relativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
