---
title: 'Procedura: specificare la catena di certificati di autorità di certificazione usata per verificare le firme (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 103d68d4ccb4cc243d28037260c1f9f380485ff6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600309"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Procedura: specificare la catena di certificati di autorità di certificazione usata per verificare le firme (WCF)
Quando Windows Communication Foundation (WCF) riceve un messaggio SOAP firmato mediante un certificato X. 509, per impostazione predefinita verifica che il certificato X. 509 sia stato emesso da un'autorità di certificazione attendibile. A tale scopo viene eseguita una ricerca in un archivio certificati per determinare se il certificato di tale autorità di certificazione è stato riconosciuto come attendibile. Affinché WCF ricerchi questa decisione, è necessario che la catena di certificati dell'autorità di certificazione sia installata nell'archivio certificati corretto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Per installare una catena di certificati dell'autorità di certificazione  
  
- Per ogni autorità di certificazione a cui un destinatario di messaggi SOAP intende ritenere attendibili i certificati X. 509 emessi da, installare la catena di certificati dell'autorità di certificazione nell'archivio certificati che WCF è configurato per recuperare i certificati X. 509 da.  
  
     Ad esempio, se un destinatario di messaggi SOAP intende ritenere attendibili i certificati X. 509 rilasciati da Microsoft, la catena di certificati dell'autorità di certificazione per Microsoft deve essere installata nell'archivio certificati in cui è configurato WCF per la ricerca di certificati X. 509 da. L'archivio certificati in cui WCF cerca i certificati X. 509 può essere specificato nel codice o nella configurazione. Ad esempio, è possibile specificare questo valore nel codice usando il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> metodo o nella configurazione in diversi modi, tra cui [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Poiché Windows offre un set incorporato di catene di certificati predefinite di autorità di certificazione attendibili, è possibile che non sia necessario installare la catena di certificati per tutte le autorità di certificazione.  
  
    1. Esportare la catena di certificati dell'autorità di certificazione.  
  
         La modalità utilizzata per eseguire questa operazione varia a seconda dell'autorità di certificazione. Se l'autorità di certificazione esegue Servizi certificati Microsoft, selezionare **Scarica un certificato CA, la catena di certificati o l'elenco CRL**, quindi scegliere **Scarica certificato CA**.  
  
    2. Importare la catena di certificati dell'autorità di certificazione.  
  
         In Microsoft Management Console (MMC), aprire lo snap-in Certificati. Per l'archivio certificati da cui WCF è configurato per recuperare i certificati X. 509, selezionare la cartella **autorità di certificazione** **radice attendibili** . Nella cartella **autorità di certificazione radice attendibili** , fare clic con il pulsante destro del mouse sulla cartella **certificati** , scegliere **tutte le attività**, quindi fare clic su **Importa**. Indicare il file esportato nel primo passaggio.  
  
         Per ulteriori informazioni sull'utilizzo dello snap-in certificati con MMC, vedere [procedura: visualizzare certificati con lo snap-in MMC](how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vedere anche

- [Working with Certificates](working-with-certificates.md)
