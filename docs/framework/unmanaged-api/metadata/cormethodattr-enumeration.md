---
title: Enumerazione CorMethodAttr
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 74088d1cd018bb07406fc7d00ff83d783a98b663
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450235"
---
# <a name="cormethodattr-enumeration"></a>Enumerazione CorMethodAttr
Contiene valori che descrivono le funzionalità di un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|`mdMemberAccessMask`|Specifica l'accesso ai membri.|  
|`mdPrivateScope`|Specifica che non è possibile fare riferimento al membro.|  
|`mdPrivate`|Specifica che il membro è accessibile solo dal tipo padre.|  
|`mdFamANDAssem`|Specifica che il membro è accessibile dai sottotipi solo nell'assembly.|  
|`mdAssem`|Specifica che il membro è accessibilmente da chiunque nell'assembly.|  
|`mdFamily`|Specifica che il membro è accessibile solo dal tipo e dai sottotipi.|  
|`mdFamORAssem`|Specifica che il membro è accessibile dalle classi derivate e da altri tipi nell'assembly.|  
|`mdPublic`|Specifica che il membro è accessibile da tutti i tipi con accesso all'ambito.|  
|`mdStatic`|Specifica che il membro è definito come parte del tipo anziché come membro di un'istanza di.|  
|`mdFinal`|Specifica che non è possibile eseguire l'override del metodo.|  
|`mdVirtual`|Specifica che il metodo può essere sottoposto a override.|  
|`mdHideBySig`|Specifica che il metodo viene nascosto in base al nome e alla firma, anziché semplicemente al nome.|  
|`mdVtableLayoutMask`|Specifica il layout della tabella virtuale.|  
|`mdReuseSlot`|Specifica che lo slot utilizzato per questo metodo nella tabella virtuale deve essere riutilizzato. Questa è l'impostazione predefinita.|  
|`mdNewSlot`|Specifica che il metodo ottiene sempre un nuovo slot nella tabella virtuale.|  
|`mdCheckAccessOnOverride`|Specifica che il metodo può essere sottoposto a override dagli stessi tipi a cui è visibile.|  
|`mdAbstract`|Specifica che il metodo non è implementato.|  
|`mdSpecialName`|Specifica che il metodo è speciale e che il nome descrive come.|  
|`mdPinvokeImpl`|Specifica che l'implementazione del metodo viene trasmessa mediante PInvoke.|  
|`mdUnmanagedExport`|Specifica che il metodo è un metodo gestito esportato nel codice non gestito.|  
|`mdReservedMask`|Riservato per uso interno da parte del Common Language Runtime.|  
|`mdRTSpecialName`|Specifica che il Common Language Runtime deve controllare la codifica del nome del metodo.|  
|`mdHasSecurity`|Specifica che al metodo è associata una sicurezza.|  
|`mdRequireSecObject`|Specifica che il metodo chiama un altro metodo che contiene il codice di sicurezza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
