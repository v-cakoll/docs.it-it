---
title: Considerazioni sulla sicurezza con metadati
ms.date: 03/30/2017
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
ms.openlocfilehash: c41ebf5c39e74932a4bade610c4e236b28444327
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601023"
---
# <a name="security-considerations-with-metadata"></a>Considerazioni sulla sicurezza con metadati
Quando si utilizzano le funzionalità dei metadati in Windows Communication Foundation (WCF), considerare le implicazioni di sicurezza relative alla pubblicazione, al recupero e all'utilizzo dei metadati del servizio.  
  
## <a name="when-to-publish-metadata"></a>Quando pubblicare metadati  
 I servizi WCF non pubblicano i metadati per impostazione predefinita. Per pubblicare metadati per un servizio WCF, è necessario abilitare in modo esplicito la pubblicazione dei metadati aggiungendo endpoint dei metadati al servizio (vedere [pubblicazione di metadati](publishing-metadata.md)). Se si lascia disabilitata la pubblicazione dei metadati, si riduce la superficie di attacco del servizio e il rischio di diffusione non intenzionale di informazioni. Non tutti i servizi devono pubblicare metadati. Se non è necessario pubblicare metadati, considerare l'ipotesi di lasciare la funzione disattivata. Si noti che è comunque possibile generare metadati e codice client direttamente dagli assembly del servizio utilizzando lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Per ulteriori informazioni sull'utilizzo di Svcutil. exe per esportare i metadati, vedere [procedura: utilizzare Svcutil. exe per esportare metadati dal codice del servizio compilato](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).  
  
## <a name="publishing-metadata-using-a-secure-binding"></a>Pubblicazione di metadati tramite un'associazione sicura  
 Le associazioni di metadati predefinite fornite da WCF non sono sicure e consentono l'accesso anonimo ai metadati. I metadati del servizio pubblicati da un servizio WCF contengono una descrizione dettagliata del servizio e possono contenere intenzionalmente o accidentalmente informazioni riservate. I metadati del servizio possono, ad esempio, contenere informazioni su operazioni dell'infrastruttura non destinate ad essere trasmesse pubblicamente. Per proteggere metadati del servizio dall'accesso non autorizzato, è possibile usare un'associazione protetta per l'endpoint dei metadati. Gli endpoint dei metadati rispondono alle richieste HTTP/GET che possono usare SSL (Secure Sockets Layer) per proteggere i metadati. Per altre informazioni, vedere [procedura: proteggere gli endpoint dei metadati](how-to-secure-metadata-endpoints.md).  
  
 La sicurezza degli endpoint dei metadati offre inoltre ai richiedenti un modo sicuro per recuperare i metadati del servizio, senza rischi di manomissioni o spoofing.  
  
## <a name="using-only-trusted-metadata"></a>Utilizzo dei soli metadati attendibili  
 È possibile usare metadati del servizio per costruire automaticamente i componenti runtime necessari per chiamare il servizio. È inoltre possibile usare i metadati in fase di progettazione, per sviluppare un'applicazione client, o in fase di esecuzione, per aggiornare dinamicamente l'associazione usata da un client per chiamare un servizio.  
  
 I metadati del servizio possono essere manomessi o sottoposti a spoofing quando vengono recuperati in modo non protetto. I metadati manomessi possono reindirizzare il client a un servizio dannoso, contenere impostazioni di sicurezza compromesse o strutture XML dannose. I documenti di metadati possono essere di grandi dimensioni e vengono spesso salvati nel file system. Per evitare manomissioni e spoofing, usare un'associazione protetta per richiedere i metadati del servizio quando diventano disponibili.  
  
## <a name="using-safe-techniques-for-processing-metadata"></a>Uso di tecniche sicure per l'elaborazione dei metadati  
 I metadati del servizio vengono spesso recuperati da un servizio su una rete usando protocolli standardizzati, ad esempio WS-MetadataExchange (MEX). Molti formati dei metadati includono meccanismi di riferimento per puntare a ulteriori metadati. Il tipo <xref:System.ServiceModel.Description.MetadataExchangeClient> elabora automaticamente i riferimenti in documenti WSDL (Web Services Description Language), XML Schema e documenti MEX. La dimensione dell'oggetto <xref:System.ServiceModel.Description.MetadataSet> creato dai metadati recuperati è direttamente proporzionale al valore di <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A> per l'istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient> usata e al valore di `MaxReceivedMessageSize` per l'associazione usata dall'istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient> in questione. Impostare queste quote sui valori appropriati, in base alle necessità dello scenario.  
  
 In WCF, i metadati del servizio vengono elaborati come XML. Quando si elaborano documenti XML, le applicazioni devono proteggersi da strutture XML dannose. Utilizzare l'oggetto <xref:System.Xml.XmlDictionaryReader> con le quote appropriate durante l'elaborazione di XML e impostare anche la <xref:System.Xml.XmlTextReader.DtdProcessing%2A> proprietà su <xref:System.Xml.DtdProcessing.Prohibit> .  
  
 Il sistema di metadati in WCF è estensibile ed è possibile registrare le estensioni dei metadati nel file di configurazione dell'applicazione. vedere [estensione del sistema di metadati](../extending/extending-the-metadata-system.md). Le estensioni dei metadati possono eseguire codice arbitrario, pertanto è necessario proteggere il file di configurazione dell'applicazione con elenchi di controllo di accesso (ACL) appropriati e registrare solo le implementazioni delle estensioni dei metadati attendibili.  
  
## <a name="validating-generated-clients"></a>Convalida dei client generati  
 Quando si genera codice client dai metadati recuperati da un'origine non attendibile, convalidare il codice client generato per verificare che il client generato sia conforme ai criteri di sicurezza dell'applicazione client. È possibile usare un comportamento di convalida per controllare le impostazioni sull'associazione client o controllare visivamente il codice generato dagli strumenti. Per un esempio di come implementare un client che convalida i comportamenti, vedere [convalida client](../samples/client-validation.md).  
  
## <a name="protecting-application-configuration-files"></a>Protezione dei file di configurazione dell'applicazione  
 Il file di configurazione dell'applicazione di un servizio può controllare come e se i metadati vengono pubblicati. È buona norma proteggere il file di configurazione dell'applicazione con elenchi di controllo di accesso (ACL) appropriati, per assicurare che l'autore di un attacco non possa modificare tali impostazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: proteggere endpoint dei metadati](how-to-secure-metadata-endpoints.md)
- [Sicurezza](security.md)
