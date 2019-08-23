---
title: 'Procedura: Ottenere un certificato (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: e720a6742506f6270fda65de12f510c2a6224873
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929183"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Procedura: Ottenere un certificato (WCF)
Per usare una delle funzionalità di Windows Communication Foundation (WCF) di che usano certificati X. 509, è sufficiente ottenere prima i certificati.  
  
### <a name="to-obtain-an-x509-certificate"></a>Per ottenere un certificato X.509  
  
1. Effettuare una delle seguenti operazioni:  
  
    - Acquistare un certificato da un'autorità di certificazione, ad esempio VeriSign, Inc.  
  
    - Configurare il proprio servizio certificati e fare in modo che un'autorità di certificazione firmi i certificati. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Datacenter Server e Windows 2000 Datacenter Server includono tutti servizi certificati che supportano l'infrastruttura a chiave pubblica (PKI). In Windows Server 2008 usare il ruolo [Servizi certificati Active Directory](https://go.microsoft.com/fwlink/?LinkID=153483) per gestire un'autorità di certificazione.  
  
    - Configurare un proprio servizio certificati e non far firmare i certificati.  
  
    > [!NOTE]
    > Indipendentemente dall'approccio adottato, il destinatario della richiesta SOAP che contiene il certificato X.509 deve considerare attendibile il certificato X.509. Questo significa che il certificato X.509 o un'autorità emittente nella catena di certificati si trova nell'archivio certificati Persone attendibili e che il certificato X.509 non si trova nell'archivio Certificati non disponibili nell'elenco locale.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Procedura: Creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
