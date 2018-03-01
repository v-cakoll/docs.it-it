---
title: 'Procedura: ottenere un certificato (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5dcefa658aec37b9af3c4f9285ec76a0d549b868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Procedura: ottenere un certificato (WCF)
Per usare una qualsiasi delle funzionalità di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che usano certificati X.509, è necessario prima ottenere i certificati.  
  
### <a name="to-obtain-an-x509-certificate"></a>Per ottenere un certificato X.509  
  
1.  Effettuare una delle seguenti operazioni:  
  
    -   Acquistare un certificato da un'autorità di certificazione, ad esempio VeriSign, Inc.  
  
    -   Configurare il proprio servizio certificati e fare in modo che un'autorità di certificazione firmi i certificati. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Datacenter Server e Windows 2000 Datacenter Server includono tutti servizi certificati che supportano l'infrastruttura a chiave pubblica (PKI). In Windows Server 2008, utilizzare il [Servizi certificati Active Directory](http://go.microsoft.com/fwlink/?LinkID=153483) ruolo per gestire un'autorità di certificazione.  
  
    -   Configurare un proprio servizio certificati e non far firmare i certificati.  
  
    > [!NOTE]
    >  Indipendentemente dall'approccio adottato, il destinatario della richiesta SOAP che contiene il certificato X.509 deve considerare attendibile il certificato X.509. Questo significa che il certificato X.509 o un'autorità emittente nella catena di certificati si trova nell'archivio certificati Persone attendibili e che il certificato X.509 non si trova nell'archivio Certificati non disponibili nell'elenco locale.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: Creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
