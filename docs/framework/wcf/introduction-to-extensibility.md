---
title: Introduzione all'estendibilità
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
ms.openlocfilehash: 8ac605b562531329333b5f05e081d89de55d8cd2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645439"
---
# <a name="introduction-to-extensibility"></a>Introduzione all'estendibilità
Il modello di applicazione Windows Communication Foundation (WCF) è progettato per soddisfare la maggior parte dei requisiti di comunicazione di qualsiasi applicazione distribuita. Esistono tuttavia scenari che non sono supportati dal modello di applicazione predefinito né dalle implementazioni fornite dal sistema. Il modello di estendibilità WCF è progettato per supportare scenari personalizzati consentendo di modificare il comportamento del sistema a ogni livello, anche al punto di sostituzione l'intero modello di applicazione. In questo argomento vengono illustrate le varie aree di estensione e vengono forniti i collegamenti alle informazioni aggiuntive relative a ogni area.  
  
## <a name="areas-to-extend"></a>Aree da estendere  
 È possibile estendere:  
  
- La fase di esecuzione dell'applicazione. Estende la distribuzione e l'elaborazione di messaggi per l'applicazione. Quest'area include anche l'estensione del sistema di sicurezza, del sistema dei metadati, del sistema della serializzazione e delle associazioni ed elementi di associazione che connettono l'applicazione al sistema di canali sottostante.  
  
- Il canale e la fase di esecuzione del canale. Estende il sistema che funziona al livello del messaggio, fornendo protocollo, trasporto e supporto di codifica.  
  
- La fase di esecuzione dell'host. Estende la relazione del dominio dell'applicazione host alla fase di esecuzione del canale e dell'applicazione.  
  
### <a name="extending-the-application-runtime"></a>Estensione della fase di esecuzione dell'applicazione  
 Nelle applicazioni di WCF, vi è una differenza tra i messaggi destinati a un canale corrispondente e sono destinati all'applicazione stessa. I messaggi del canale supportano alcune funzionalità correlate al canale, ad esempio quella che consente di stabilire una conversazione protetta o una sessione affidabile. Questi messaggi non sono disponibili nella fase di esecuzione dell'applicazione. Vengono elaborati prima che venga coinvolto il livello dell'applicazione.  
  
 I messaggi dell'applicazione contengono dati destinati a un'operazione client o di servizio creata personalmente o dal cliente. Questi messaggi sono disponibili nel sistema di estensione al livello dell'applicazione in formato messaggio o oggetto, a seconda delle esigenze specifiche.  
  
 Tutti i messaggi passano attraverso il sistema di canali. Solo i messaggi dell'applicazione vengono passati dal sistema di canali nell'applicazione. Per creare una nuova funzionalità a livello di canale, è necessario estendere il sistema di canali. Per creare nuove funzionalità a livello di applicazione, è necessario estendere la fase di esecuzione del servizio o del client (dispatcher e channel factory rispettivamente). Per altre informazioni sull'estensione del runtime dell'applicazione, vedere [Extending ServiceHost and the Service Model Layer](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### <a name="extending-security"></a>Estensione della protezione  
 Per creare meccanismi di sicurezza personalizzati, quali token e credenziali, è necessario estendere il sistema di sicurezza. Per altre informazioni, vedere [estensione di sicurezza](../../../docs/framework/wcf/extending/extending-security.md).  
  
#### <a name="extending-metadata"></a>Estensione di metadati  
 Per esporre i metadati diversamente dall'impostazione predefinita, è necessario estendere il sistema dei metadati. Per altre informazioni, vedere [estensione del sistema di metadati](../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
#### <a name="extending-serialization"></a>Estensione della serializzazione  
 Per compilare codificatori personalizzati, fornire surrogati dei dati o eseguire altre operazioni che comportano la personalizzazione di dati trasferiti, è necessario estendere il sistema di serializzazione. Per altre informazioni, vedere [estensione di codificatori e serializzatori](../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md).  
  
#### <a name="extending-bindings"></a>Estensione delle associazioni  
 Per associare canali del trasporto o del protocollo al livello dell'applicazione, è necessario estendere il sistema delle associazioni. Per altre informazioni, vedere [estensione delle associazioni](../../../docs/framework/wcf/extending/extending-bindings.md).  
  
### <a name="extending-the-channel-system"></a>Estensione del sistema di canali  
 Per creare canali che supportano i trasporti personalizzati o funzionalità del protocollo, vedere [estensione del livello del canale](../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
### <a name="extending-the-service-hosting-system"></a>Estensione del sistema host del servizio  
 Per modificare il modello di applicazione a livello di servizio, è necessario estendere la classe <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>. Per altre informazioni, vedere [Extending ServiceHost and the Service Model Layer](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Per modificare la relazione tra il dominio dell'applicazione host e l'host del servizio, è necessario estendere la classe <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>. Per altre informazioni, vedere [estensione di Hosting tramite ServiceHostFactory](../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estensione di WCF](../../../docs/framework/wcf/extending/index.md)
