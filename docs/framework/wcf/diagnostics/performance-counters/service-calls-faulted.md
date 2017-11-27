---
title: 'Servizio: chiamate con errori'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f82558bdacbc36569329764aa1639c81146d9127
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted"></a>Servizio: chiamate con errori
Nome contatore: chiamate con errori  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate a questo servizio che hanno restituito errori. Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP. Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva. Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.  
  
## <a name="see-also"></a>Vedere anche  
 [Specifica e gestione degli errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
