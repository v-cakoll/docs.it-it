---
title: Enumerazione AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e7b73559e8def890f8df8f596fbe8ad5bb5d3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777477"
---
# <a name="assemblyoptions-enumeration"></a>Enumerazione AssemblyOptions
Enumera le opzioni dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Campi  
  
|Campo|Descrizione|  
|-----------|-----------------|  
|optAssemTitle|String: rappresenta il titolo dell'assembly.|  
|optAssemDescription|String: contiene la descrizione dell'assembly.|  
|optAssemConfig|Stringa: contiene la configurazione dell'assembly.|  
|optAssemOS|Codificata come stringa: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Stringa: contiene le impostazioni locali dell'assembly.|  
|optAssemVersion|Codificata in stringa come: "Major. minor. Build. Revision".|  
|optAssemCompany|Stringa: contiene l'azienda.|  
|optAssemProduct|Stringa: contiene il nome del prodotto.|  
|optAssemProductVersion|Stringa (nota anche come InformationalVersion).|  
|optAssemCopyright|Stringa: contiene le informazioni sul copyright.|  
|optAssemTrademark|Stringa: contiene le informazioni sul marchio.|  
|optAssemKeyFile|Stringa (nome file).|  
|optAssemKeyName|Stringa (il nome della chiave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (noto anche come DelaySign).|  
|optAssemFileVersion|Codificata in formato stringa come "Major. minor. Build. Revision", uguale a ProductVersion.|  
|optAssemSatelliteVer|Codificata in formato stringa come "Major. minor. Build. Revision".|  
|optLastAssemOption|Contatore del numero di elementi.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ALink. h  
  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
