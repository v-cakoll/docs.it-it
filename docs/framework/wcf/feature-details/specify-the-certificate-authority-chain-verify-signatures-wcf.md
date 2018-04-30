---
title: 'Procedura: specificare la catena di certificati di autorità di certificazione usata per verificare le firme (WCF)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29637ea7f0a1e533a6735ebfa6f428fe20039e48
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Procedura: specificare la catena di certificati di autorità di certificazione usata per verificare le firme (WCF)
Per impostazione predefinita, quando riceve un messaggio SOAP firmato mediante un certificato X.509, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verifica che quest'ultimo venga emesso da un'autorità di certificazione attendibile. A tale scopo viene eseguita una ricerca in un archivio certificati per determinare se il certificato di tale autorità di certificazione è stato riconosciuto come attendibile. Affinché [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia in grado di svolgere questa ricerca è necessario che la catena di certificati dell'autorità di certificazione sia installata nell'archivio certificati corretto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Per installare una catena di certificati dell'autorità di certificazione  
  
-   Per ogni autorità di certificazione i cui certificati X.509 vengono ritenuti attendibili da destinatario di messaggi SOAP, installare la relativa catena di certificati nell'archivio certificati configurato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] come origine dei certificati X.509.  
  
     Ad esempio, se un destinatario di messaggi SOAP intende ritenere attendibili i certificati X.509 rilasciati da Microsoft, è necessario installare la catena di certificati dell'autorità di certificazione di Microsoft nell'archivio certificati in cui [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ricerca i certificati X.509. L'archivio certificati nel quale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] esegue la ricerca dei certificati X.509 può essere specificato in codice o in configurazione. Ad esempio, questo valore può essere specificato nel codice utilizzando il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> metodo o nella configurazione alcuni modi, ad esempio il [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Poiché Windows offre un set incorporato di catene di certificati predefinite di autorità di certificazione attendibili, è possibile che non sia necessario installare la catena di certificati per tutte le autorità di certificazione.  
  
    1.  Esportare la catena di certificati dell'autorità di certificazione.  
  
         La modalità utilizzata per eseguire questa operazione varia a seconda dell'autorità di certificazione. Se l'autorità di certificazione esegue Servizi certificati Microsoft, selezionare **scarica un certificato CA, una catena di certificati o CRL**, quindi scegliere **Esegui Download certificato CA**.  
  
    2.  Importare la catena di certificati dell'autorità di certificazione.  
  
         In Microsoft Management Console (MMC), aprire lo snap-in Certificati. Per il certificato archiviare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è configurato per recuperare i certificati x. 509, selezionare il **radice attendibili** **autorità di certificazione**cartella. Sotto il **autorità di certificazione radice attendibili** cartella, fare doppio clic su di **certificati**cartella, scegliere **tutte le attività**e quindi fare clic su **importazione** . Indicare il file esportato nel primo passaggio.  
  
         Per ulteriori informazioni sull'utilizzo dello snap-in certificati in MMC, vedere [procedura: visualizzare certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
