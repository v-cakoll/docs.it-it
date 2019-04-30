---
title: Risorse del sistema operativo richieste da WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955220"
---
# <a name="operating-system-resources-required-by-wcf"></a>Risorse del sistema operativo richieste da WCF
Windows Communication Foundation (WCF) dipende da diverse risorse fornite dal sistema operativo alla funzione. Nella tabella seguente vengono elencate tali risorse.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|Microsoft Distributed Transaction Coordinator (MSDTC)|Necessario per supportare le transazioni OleTx.|  
|Internet Information Services (IIS)|Necessario se si desidera usare IIS per ospitare l'applicazione.|  
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|Necessario se si desidera usare WAS per ospitare l'applicazione.|  
  
## <a name="see-also"></a>Vedere anche

- [Requisiti di sistema](../../../docs/framework/wcf/wcf-system-requirements.md)
