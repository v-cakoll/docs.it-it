---
title: 'Procedura: ottenere un certificato (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: bfe6dcfe6850ee17a7bbb59f3a6ccad6c3c3e7d7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964236"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Procedura: ottenere un certificato (WCF)
Per usare una delle funzionalità di Windows Communication Foundation (WCF) di che usano certificati X. 509, è sufficiente ottenere prima i certificati.  
  
### <a name="to-obtain-an-x509-certificate"></a>Per ottenere un certificato X.509  
  
1. Effettuare una delle seguenti operazioni:  
  
    - Acquistare un certificato da un'autorità di certificazione, ad esempio VeriSign, Inc.  
  
    - Configurare il proprio servizio certificati e fare in modo che un'autorità di certificazione firmi i certificati. Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter e Windows 2000 Datacenter Server includono tutti servizi certificati che supportano l'infrastruttura a chiave pubblica (PKI). In Windows Server 2008 usare il ruolo [Servizi certificati Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) per gestire un'autorità di certificazione.  
  
    - Configurare un proprio servizio certificati e non far firmare i certificati.  
  
    > [!NOTE]
    > Indipendentemente dall'approccio adottato, il destinatario della richiesta SOAP che contiene il certificato X.509 deve considerare attendibile il certificato X.509. Questo significa che il certificato X.509 o un'autorità emittente nella catena di certificati si trova nell'archivio certificati Persone attendibili e che il certificato X.509 non si trova nell'archivio Certificati non disponibili nell'elenco locale.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Procedura: Creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
