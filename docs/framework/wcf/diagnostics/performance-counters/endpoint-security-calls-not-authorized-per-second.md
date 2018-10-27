---
title: 'Endpoint: chiamate di sicurezza non autorizzate al secondo'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: c62bec570daf8b107ca0540871eb6eac43ca2d7e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188352"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a>Endpoint: chiamate di sicurezza non autorizzate al secondo
Nome contatore: chiamate di sicurezza non autorizzate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di messaggi in ingresso al secondo provenienti da un utente valido e adeguatamente protetti, ma per cui l'utente non è autorizzato a eseguire attività specifiche.  
  
 Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
