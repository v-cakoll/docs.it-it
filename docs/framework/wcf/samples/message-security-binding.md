---
title: Associazioni di sicurezza ai messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f0c8b125d3fc313dca4140b871ccea8165329fda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-binding"></a>Associazioni di sicurezza ai messaggi
Contenuto della sezione sono contenuti esempi che illustrano l'associazione della sicurezza ai messaggi in Windows Services in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="in-this-section"></a>In questa sezione  
 [Sicurezza dei messaggi anonima](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 In questo esempio viene illustrato come implementare un'applicazione di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che utilizza la sicurezza a livello di messaggi senza autenticazione del client, ma che richiede l'autenticazione del server utilizzando il certificato X.509 del server.  
  
 [Certificato di sicurezza dei messaggi](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 In questo esempio viene illustrato come implementare un'applicazione che utilizza WS-Security con l'autenticazione del certificato X.509 v3 per il client e che richiede l'autenticazione del server utilizzando il certificato X.509 v3 del server.  
  
 [Sicurezza dei messaggi tramite nome utente](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 In questo esempio viene illustrato come implementare un'applicazione che usa WS-Security con l'autenticazione del nome utente per il client e richiede l'autenticazione del server tramite il certificato X.509v3 del server.  
  
 [Sicurezza dei messaggi di Windows](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 In questo esempio viene illustrato come configurare un'associazione <xref:System.ServiceModel.WSHttpBinding> per usare la sicurezza a livello di messaggio con autenticazione Windows.
