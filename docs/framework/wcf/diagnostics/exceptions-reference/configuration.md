---
title: Configurazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86a6e12f-73b5-450e-8725-f4ca5fe0702c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3eee9f955ca75d799b9e5384e47df527934a595f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="configuration"></a>Configurazione
In questo argomento vengono elencate tutte le eccezioni generate dalla configurazione di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|ConfigBindingCannotBeConfigured|Impossibile configurare l'associazione sull'endpoint del servizio.|  
|ConfigElementKeyNull|La chiave dell'elemento di configurazione specifico non può essere Null.|  
|ConfigExtensionTypeNotRegisteredInCollection|L'estensione del tipo specificato non è registrata nella raccolta di estensioni indicata.|  
|ConfigIndexOutOfRange|Il valore per l'attributo specificato non è compreso nell'intervallo valido.|  
|ConfigInvalidBindingConfigurationName|La configurazione specificata non dispone di un'associazione con il nome indicato.|  
|ConfigInvalidBindingName|La configurazione specificata non dispone di un'associazione con il nome indicato. Si tratta di un valore non valido per l'associazione.|  
|ConfigInvalidCommonEndpointBehaviorType|Impossibile aggiungere l'estensione di comportamento specificata al comportamento dell'endpoint comune perché non implementa il tipo indicato.|  
|ConfigInvalidCommonServiceBehaviorType|Impossibile aggiungere l'estensione di comportamento specificata al comportamento del servizio comune perché non implementa il tipo indicato.|  
|ConfigInvalidEndpointBehaviorType|Impossibile aggiungere l'estensione di comportamento specificata al comportamento dell'endpoint indicato perché il tipo di comportamento sottostante non implementa l'interfaccia IServiceBehavior.|  
|ConfigInvalidExtensionType|Il tipo specificato deve derivare dall'estensione indicata da utilizzare nella raccolta.|  
|ConfigInvalidServiceBehaviorType|Impossibile aggiungere l'estensione di comportamento al comportamento del servizio con il nome specificato perché il tipo di comportamento sottostante non implementa l'interfaccia IServiceBehavior.|  
|ConfigMessageEncodingAlreadyInBinding|Impossibile aggiungere lo specifico elemento di codifica messaggi. Nell'associazione specificata esiste già un altro elemento di codifica messaggi. Per ogni associazione è consentito solo un elemento di codifica messaggi.|  
|ConfigNoExtensionCollectionAssociatedWithType|Impossibile trovare la raccolta di estensioni associata all'estensione del tipo specificato.|  
|ConfigSectionNotFound|Impossibile creare la sezione di configurazione specificata. Il file Machine.config non contiene le informazioni necessarie. Verificare che la sezione di configurazione sia stata registrata correttamente e che il nome di sezione digitato non contenga errori. Per le sezioni di Windows Communication Foundation, eseguire ServiceModelReg.exe - i per correggere l'errore.|  
|ConfigTransportAlreadyInBinding|Impossibile aggiungere lo specifico elemento trasporto. Nella specifica associazione esiste già un altro elemento trasporto. Per ogni associazione è consentito solo un elemento di codifica messaggi.|
