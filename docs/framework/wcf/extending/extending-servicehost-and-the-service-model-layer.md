---
title: Estensione di ServiceHost e del livello del modello di servizi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1a1a439735375d96bee2d09f13d50e43783df964
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>Estensione di ServiceHost e del livello del modello di servizi
Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante. Le estensioni del modello di servizi modificano o implementano il comportamento e le funzioni dell'esecuzione o della comunicazione relativamente a funzionalità del client o del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Estensione dei client](../../../../docs/framework/wcf/extending/extending-clients.md)  
 Vengono descritte le interfacce in grado di intercettare e modificare la fase di esecuzione del client, nonché le classi nelle quali è possibile inserire estensioni personalizzate nelle applicazioni client. È ad esempio possibile eseguire la registrazione dei messaggi del client personalizzata, la serializzazione dei messaggi personalizzata e così via.  
  
 [Estensione di Dispatcher](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 Vengono descritte le interfacce in grado di intercettare e modificare la fase di esecuzione del servizio, nonché le classi nelle quali è possibile inserire estensioni personalizzate nelle applicazioni del servizio. È ad esempio possibile eseguire la registrazione del servizio personalizzata, la convalida dei messaggi dal lato del servizio, la distribuzione personalizzata e così via.  
  
 [Oggetti estensibili](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 Vengono descritti i cinque oggetti estendibili e il modello <xref:System.ServiceModel.IExtensibleObject%601>. Questo modello viene usato per estendere le classi di runtime esistenti con nuove funzionalità oppure per aggiungere un nuovo stato a un oggetto. Le estensioni, allegate a uno degli oggetti estensibili, attivano i comportamenti in fasi molto diverse dell'elaborazione per accedere a stato e funzionalità condivisi allegati a un oggetto estensibile comune al quale possono accedere.  
  
 [La configurazione e l'estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 Per modificare le impostazioni o per inserire estensioni nella fase di esecuzione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si utilizzano i comportamenti. WCF comprende comportamenti implementati dal sistema per controllare la limitazione delle richieste, la creazione di istanze e molti altri aspetti di servizi e operazioni. Contenuto della sezione viene descritto come creare comportamenti personalizzati e come renderli disponibili per l'utilizzo sia a livello di programmazione che nei file di configurazione.  
  
 [Estensione dell'Hosting tramite ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 Viene descritto come estendere <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> e come utilizzare le classi <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> per personalizzare l'ambiente host.  
  
## <a name="reference"></a>Riferimento  
  
## <a name="related-sections"></a>Sezioni correlate
