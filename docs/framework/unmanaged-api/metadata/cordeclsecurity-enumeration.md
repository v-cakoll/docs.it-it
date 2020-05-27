---
title: Enumerazione CorDeclSecurity
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: ffbc9a10ff48b3dfd59b95c0f6b9ecab80b6a49c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007884"
---
# <a name="cordeclsecurity-enumeration"></a>Enumerazione CorDeclSecurity
Specifica le azioni relative alla sicurezza che possono essere eseguite con la sicurezza dichiarativa.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`dclActionMask`|Riservato.|  
|`dclActionNil`|Riservato.|  
|`dclRequest`|Riservato.|  
|`dclDemand`|A tutti i chiamanti nella parte superiore dello stack di chiamate deve essere concessa l'autorizzazione specificata dall'oggetto di autorizzazione corrente.|  
|`dclAssert`|Il codice chiamante può accedere alla risorsa identificata dall'oggetto di autorizzazione corrente, anche se ai chiamanti più in alto nello stack non è stata concessa l'autorizzazione per accedere alla risorsa|  
|`dclDeny`|La possibilità di accedere alla risorsa specificata dall'oggetto di autorizzazione corrente viene negata ai chiamanti, anche se è stata concessa l'autorizzazione per accedervi.|  
|`dclPermitOnly`|È possibile accedere solo alle risorse specificate dall'oggetto di autorizzazione, anche se al codice è stata concessa l'autorizzazione per accedere ad altre risorse.|  
|`dclLinktimeCheck`|Al chiamante immediato è necessario concedere l'autorizzazione specificata per un determinato periodo di tempo.|  
|`dclInheritanceCheck`|Alla classe derivata che eredita un'altra classe o che esegue l'override di un metodo è necessario concedere l'autorizzazione specificata.|  
|`dclRequestMinimum`|Il chiamante può richiedere le autorizzazioni minime necessarie per l'esecuzione del codice. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclRequestOptional`|Il chiamante può richiedere autorizzazioni aggiuntive facoltative (non necessarie per l'esecuzione). Con questa richiesta viene implicitamente rifiutata ogni altra autorizzazione che non sia stata esplicitamente richiesta. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclRequestRefuse`|La richiesta del chiamante per le autorizzazioni che potrebbero essere impiegate in uso non verrà concessa. Questa azione può essere usata solo nell'ambito dell'assembly.|  
|`dclPrejitGrant`|Riservato.|  
|`dclPrejitDenied`|Riservato.|  
|`dclNonCasDemand`|Riservato.|  
|`dclNonCasLinkDemand`|È necessario concedere al chiamante diretto l'autorizzazione specificata.|  
|`dclNonCasInheritance`|Riservato.|  
|`dclLinkDemandChoice`|Riservato.|  
|`dclInheritanceDemandChoice`|Riservato.|  
|`dclDemandChoice`|Riservato.|  
|`dclMaximumValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
