---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715934"
---
# <a name="security-etw-events"></a>Eventi ETW di sicurezza

Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1  
 La tabella seguente illustra la parola chiave e il livello Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Inizio della verifica del nome sicuro.|  
|`StrongNameVerificationStop_V1`|182|Fine della verifica del nome sicuro.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Flag di verifica.|  
|ErrorCode|win:UInt32|Codice errore HResult.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Nome completo dell'assembly.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1  
 La tabella seguente illustra la parola chiave e il livello  
  
|Parola chiave per la generazione dell'evento|Livello|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|Informativo (4)|  
  
 La tabella seguente mostra le informazioni sull'evento.  
  
|Event|ID evento|Generato quando|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Inizio della verifica Authenticode.|  
|`AuthenticodeVerificationStop_V1`|184|Fine della verifica Authenticode.|  
  
 La tabella seguente mostra i dati dell'evento.  
  
|Nome del campo|Tipo di dati|Descrizione|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Flag di verifica.|  
|ErrorCode|win:UInt32|Codice errore HResult.|  
|ModulePath|win:UnicodeString|Percorso del modulo.|  
|ClrInstanceID|win:UInt16|ID univoco per l'istanza di CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vedere anche

- [Eventi ETW di CLR](clr-etw-events.md)
