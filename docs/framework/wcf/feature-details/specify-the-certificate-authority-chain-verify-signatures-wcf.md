---
title: "Procedura: Specificare la catena di certificati dell'autorità utilizzata per verificare le firme (WCF)"
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 8d44e9f9278a212813fca5e77ebfca72734c60d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648784"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Procedura: Specificare la catena di certificati dell'autorità utilizzata per verificare le firme (WCF)
Quando Windows Communication Foundation (WCF) riceve un messaggio SOAP firmato mediante un certificato X.509, per impostazione predefinita verifica che il certificato X.509 emesso da un'autorità di certificazione attendibile. A tale scopo viene eseguita una ricerca in un archivio certificati per determinare se il certificato di tale autorità di certificazione è stato riconosciuto come attendibile. Affinché WCF a tal fine, la catena di certificati di autorità di certificazione deve essere installata nell'archivio certificati corretto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Per installare una catena di certificati dell'autorità di certificazione  
  
-   Per ogni autorità di certificazione che un destinatario di messaggi SOAP intende ritenere attendibili i certificati X.509 rilasciati da, installare la catena di certificati di autorità di certificazione nell'archivio certificati che WCF sia configurato per il recupero dei certificati X.509.  
  
     Ad esempio, se un destinatario di messaggi SOAP intende ritenere attendibili i certificati X.509 rilasciati da Microsoft, la catena di certificati di autorità di certificazione per Microsoft deve essere installata nell'archivio certificati che WCF è configurato per la ricerca i certificati X.509. È possibile specificare l'archivio certificati in cui WCF è simile per i certificati X.509 nel codice o configurazione. Ad esempio, questo valore può essere specificato nel codice utilizzando il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> metodo o nella configurazione svariati modi, tra cui la [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Poiché Windows offre un set incorporato di catene di certificati predefinite di autorità di certificazione attendibili, è possibile che non sia necessario installare la catena di certificati per tutte le autorità di certificazione.  
  
    1.  Esportare la catena di certificati dell'autorità di certificazione.  
  
         La modalità utilizzata per eseguire questa operazione varia a seconda dell'autorità di certificazione. Se l'autorità di certificazione esegue Servizi certificati Microsoft, selezionare **scarica un certificato della CA, la catena di certificati o CRL**, quindi scegliere **Esegui Download certificato CA**.  
  
    2.  Importare la catena di certificati dell'autorità di certificazione.  
  
         In Microsoft Management Console (MMC), aprire lo snap-in Certificati. Per l'archivio certificati che WCF è configurato per recuperare i certificati X.509 da, selezionare la **radice attendibili** **autorità di certificazione** cartella. Sotto il **autorità di certificazione radice attendibili** cartella, fare doppio clic sui **certificati** cartella, scegliere **tutte le attività**e quindi fare clic su **importazione** . Indicare il file esportato nel primo passaggio.  
  
         Per altre informazioni sull'utilizzo lo snap-in certificati di MMC, vedere [come: Visualizzare i certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vedere anche
- [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
