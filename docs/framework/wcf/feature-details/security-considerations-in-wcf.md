---
title: Considerazioni sulla sicurezza in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601036"
---
# <a name="security-considerations-in-wcf"></a>Considerazioni sulla sicurezza in WCF
Negli argomenti di questa sezione sono elencati i vari elementi correlati alla sicurezza da considerare durante la progettazione di un'applicazione Windows Communication Foundation (WCF).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Divulgazione di informazioni](information-disclosure.md)  
 Illustra le varie modalità in cui è possibile diffondere o lanciare attacchi alle informazioni e come limitare il problema  
  
 [Elevazione dei privilegi](elevation-of-privilege.md)  
 Descrive gli effetti causati quando all'autore di un attacco vengono assegnate autorizzazioni che vanno oltre quelle concesse inizialmente e come circoscrivere il problema.  
  
 [Attacco Denial of Service](denial-of-service.md)  
 Descrive ciò che avviene quando un sistema non è in grado di elaborare messaggi in modo appropriato e come limitare il problema.  
  
 [Manomissione](tampering.md)  
 Descrive la modifica dei messaggi o del recapito dei messaggi e come limitare il problema.  
  
 [Attacchi di tipo replay](replay-attacks.md)  
 Descrive ciò che avviene quando l'autore dell'attacco copia un flusso di messaggi tra due parti e lo riproduce verso una o più delle parti e spiega come limitare il problema.  
  
 [Considerazioni sulla protezione per le sessioni protette](security-considerations-for-secure-sessions.md)  
 Descrive gli elementi seguenti che influiscono sulla protezione durante l'implementazione di sessioni protette.  
  
 [Scenari non supportati](unsupported-scenarios.md)  
 Elenca i diversi scenari che non supportano un particolare aspetto della protezione e che devono essere evitati o presi in considerazione.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Indicazioni di sicurezza e procedure consigliate](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza](security.md)
