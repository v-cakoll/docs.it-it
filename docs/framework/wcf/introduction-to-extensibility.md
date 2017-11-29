---
title: "Introduzione all'estendibilità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0b53ec29f973760237133003c2f582e1a33a9f83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-extensibility"></a>Introduzione all'estendibilità
Il modello dell'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] è progettato per soddisfare la maggior parte dei requisiti di comunicazione di qualsiasi applicazione distribuita. Esistono tuttavia scenari che non sono supportati dal modello di applicazione predefinito né dalle implementazioni fornite dal sistema. Il modello di estendibilità [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] deve supportare scenari personalizzati consentendo di modificare il comportamento del sistema a ogni livello, anche al punto di sostituire l'intero modello di applicazione. In questo argomento vengono illustrate le varie aree di estensione e vengono forniti i collegamenti alle informazioni aggiuntive relative a ogni area.  
  
## <a name="areas-to-extend"></a>Aree da estendere  
 È possibile estendere:  
  
-   La fase di esecuzione dell'applicazione. Estende la distribuzione e l'elaborazione di messaggi per l'applicazione. Quest'area include anche l'estensione del sistema di sicurezza, del sistema dei metadati, del sistema della serializzazione e delle associazioni ed elementi di associazione che connettono l'applicazione al sistema di canali sottostante.  
  
-   Il canale e la fase di esecuzione del canale. Estende il sistema che funziona al livello del messaggio, fornendo protocollo, trasporto e supporto di codifica.  
  
-   La fase di esecuzione dell'host. Estende la relazione del dominio dell'applicazione host alla fase di esecuzione del canale e dell'applicazione.  
  
### <a name="extending-the-application-runtime"></a>Estensione della fase di esecuzione dell'applicazione  
 Nelle applicazioni [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] viene fatta distinzione tra i messaggi destinati a un canale corrispondente e quelli destinati all'applicazione stessa. I messaggi del canale supportano alcune funzionalità correlate al canale, ad esempio quella che consente di stabilire una conversazione protetta o una sessione affidabile. Questi messaggi non sono disponibili nella fase di esecuzione dell'applicazione. Vengono elaborati prima che venga coinvolto il livello dell'applicazione.  
  
 I messaggi dell'applicazione contengono dati destinati a un'operazione client o di servizio creata personalmente o dal cliente. Questi messaggi sono disponibili nel sistema di estensione al livello dell'applicazione in formato messaggio o oggetto, a seconda delle esigenze specifiche.  
  
 Tutti i messaggi passano attraverso il sistema di canali. Solo i messaggi dell'applicazione vengono passati dal sistema di canali nell'applicazione. Per creare una nuova funzionalità a livello di canale, è necessario estendere il sistema di canali. Per creare nuove funzionalità a livello di applicazione, è necessario estendere la fase di esecuzione del servizio o del client (dispatcher e channel factory rispettivamente). [!INCLUDE[crabout](../../../includes/crabout-md.md)]estensione del runtime di applicazione, vedere [estensione ServiceHost e il livello del modello di servizio](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
#### <a name="extending-security"></a>Estensione della protezione  
 Per creare meccanismi di sicurezza personalizzati, quali token e credenziali, è necessario estendere il sistema di sicurezza. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione della protezione](../../../docs/framework/wcf/extending/extending-security.md).  
  
#### <a name="extending-metadata"></a>Estensione di metadati  
 Per esporre i metadati diversamente dall'impostazione predefinita, è necessario estendere il sistema dei metadati. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione del sistema di metadati](../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
#### <a name="extending-serialization"></a>Estensione della serializzazione  
 Per compilare codificatori personalizzati, fornire surrogati dei dati o eseguire altre operazioni che comportano la personalizzazione di dati trasferiti, è necessario estendere il sistema di serializzazione. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione codificatori e serializzatori](../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md).  
  
#### <a name="extending-bindings"></a>Estensione delle associazioni  
 Per associare canali del trasporto o del protocollo al livello dell'applicazione, è necessario estendere il sistema delle associazioni. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione delle associazioni](../../../docs/framework/wcf/extending/extending-bindings.md).  
  
### <a name="extending-the-channel-system"></a>Estensione del sistema di canali  
 Per creare canali che supportano i trasporti personalizzati o funzionalità del protocollo, vedere [estendendo il livello del canale](../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
### <a name="extending-the-service-hosting-system"></a>Estensione del sistema host del servizio  
 Per modificare il modello di applicazione a livello di servizio, è necessario estendere la classe <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione ServiceHost e il livello del modello di servizio](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md).  
  
 Per modificare la relazione tra il dominio dell'applicazione host e l'host del servizio, è necessario estendere la classe <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Estensione dell'Hosting tramite ServiceHostFactory](../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Estensione di WCF](../../../docs/framework/wcf/extending/extending-wcf.md)
