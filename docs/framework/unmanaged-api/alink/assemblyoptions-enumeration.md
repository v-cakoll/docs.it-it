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
ms.openlocfilehash: e3926a0d49b2db02cf52a3cc943b05edc4cc36a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406285"
---
# <a name="assemblyoptions-enumeration"></a>Enumerazione AssemblyOptions
Enumera le opzioni di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|optAssemTitle|Stringa - rappresenta il titolo dell'assembly.|  
|optAssemDescription|Stringa - contiene la descrizione dell'assembly.|  
|optAssemConfig|Stringa - contiene la configurazione dell'assembly.|  
|optAssemOS|Stringa - codificata come: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Stringa - contiene le impostazioni locali di assembly.|  
|optAssemVersion|Stringa - codificata come: "Principale".|  
|optAssemCompany|Stringa - contiene la società.|  
|optAssemProduct|Stringa - contiene il nome del prodotto.|  
|optAssemProductVersion|Stringa (noto anche come InformationalVersion).|  
|optAssemCopyright|Stringa - contiene le informazioni sul copyright.|  
|optAssemTrademark|Stringa - contiene le informazioni sul marchio.|  
|optAssemKeyFile|String (nome file).|  
|optAssemKeyName|Stringa (il nome della chiave).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (anche noto come DelaySign).|  
|optAssemFileVersion|Stringa - codificata come "Revisione", corrisponde a ProductVersion.|  
|optAssemSatelliteVer|Stringa - codificata come "Revisione".|  
|optLastAssemOption|Un contatore del numero di elementi.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** alink.h  
  
 **Libreria**: ALink. dll  
  
## <a name="see-also"></a>Vedere anche  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
